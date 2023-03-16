# EricssonChallangeHelm

This repo contains the files used to create a helm chart.
To create this, a directory titled 'hello-chart' was created.
Inside this, a helm chart was created using:
helm create hello-chart

Next, the values.yaml file was edited to use the specified docker image at image.repo and image.tag positions

Another necessary change was to change the port in templates/service.yaml file to 8080 from 80

After this, the helm install --dry-run hello-chart . command was used to check for possible installation failures

Upon receiving no errors, the chart was installed by setting the service type to NodePort using the following command:
helm install hello-chart . --set service.type=NodePort

Then the received IP was run on the browser, which gave the following output:
<img width="357" alt="Screenshot 2023-03-15 at 11 38 16 PM" src="https://user-images.githubusercontent.com/64781077/225510745-98bd0872-61bd-4964-ba0e-e4131bc54b11.png">

Finally, this was packaged using helm package hello-chart, resulting in a .tgz file

For the next step, to install a helm chart, required only one command:
helm install hello-chart-new hello-chart-0.1.0.tgz

Upon running this, a few export commands were received, which print the IP that will display the deployed application. And the output of that is:
<img width="1335" alt="Screenshot 2023-03-15 at 11 45 35 PM" src="https://user-images.githubusercontent.com/64781077/225511054-36359558-2386-4743-a198-ba64b0fdf596.png">
