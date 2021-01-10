# Jenkins_Project
The Spring PetClinic is a sample application designed to show how the Spring stack can be used to build simple, but powerful database-oriented applications. The official version of PetClinic demonstrates the use of Spring Boot with Spring MVC and Spring Data JPA.

https://spring-petclinic.github.io/#:~:text=The%20Spring%20PetClinic%20is%20a,MVC%20and%20Spring%20Data%20JPA.

## Project-1 => Creating a multistage pipeline and viewing using build pipeline plugin

Prerequisite: jenkins installed locally and configured.

Step-1: 

A.  Let create a job at jenkins

![Screenshot (1066)](https://user-images.githubusercontent.com/46487696/104103669-6ddc7280-52c9-11eb-8ddf-0434f67b2ff6.png)

Here either select FreeStyle project after this we have to configure maven to make a build. and For this first we have to install a plugin i.e "PIPELINE MAVEN INTEGRATION".

Or you can diretly select maven project while creating job at jenkins.

Let's create a freestyle project says **Compile_petClinic**. You will redirect to the configuration part. First Go to SCM  and provide Git version project link with a proper branch specifier. Here we have taken the source code of Spring petClinic. 

Project link => https://github.com/kushagra67414/SpringPetClinic.git

![Screenshot (1051)](https://user-images.githubusercontent.com/46487696/104103736-bac04900-52c9-11eb-9dd8-68e9878e0b98.png)

![Screenshot (1052)](https://user-images.githubusercontent.com/46487696/104104085-f1975e80-52cb-11eb-9c4c-2aa5701046c7.png)


Now Configure your maven =>

go to Build > click on "Add Build Setup" > invoke top-level maven targets > Select the maven which you have configured globally or if maven is setup locally then give the path of maven folder in the system.

![Screenshot (1053)](https://user-images.githubusercontent.com/46487696/104104087-f2c88b80-52cb-11eb-98a5-e2e19994052d.png)
![Screenshot (1054)](https://user-images.githubusercontent.com/46487696/104104088-f3612200-52cb-11eb-9479-8c1b97075874.png)


Now, Click on the Build now  to have a build of a project and check if the build get Success of Failed.

![Screenshot (1055)](https://user-images.githubusercontent.com/46487696/104104288-222bc800-52cd-11eb-9ae9-d770919267b5.png)
t
Similarly create a test petclinic job at jenkins. Let's say **test_petClinic**.

![Screenshot (1056)](https://user-images.githubusercontent.com/46487696/104104339-63bc7300-52cd-11eb-8eca-8bd816c4008e.png)
![Screenshot (1057)](https://user-images.githubusercontent.com/46487696/104104340-64eda000-52cd-11eb-97e2-d7e5d06e0fa2.png)
![Screenshot (1058)](https://user-images.githubusercontent.com/46487696/104104342-64eda000-52cd-11eb-9417-c68b0574b4cd.png)



## Project-2 => triggering test job after trigerring the other job first.

Here, if we want to trigger test_petClinic job we can set BUILD TRIGGERS of another job, So that if the given job get triggered the other automatically get trigger.

Let's see in below output =>

We will trigger Test_petClinic job with the help of Compile_petClinic job

Go to test_petClinic configuration part > build trigger > Select "BUILD AFTER OTHER PROJECTS ARE BUILT" > give the project/job so that your current job can trigger after the build of this job.

![Screenshot (1059)](https://user-images.githubusercontent.com/46487696/104123069-e9442f80-536e-11eb-9309-645f8d23b252.png)


## Project-3 => Create a Multistage pipeline and viewing using "Build Pipeline Plugin" 

Here, First Download the given plugin i.e Build Pipeline.

![Screenshot (1060)](https://user-images.githubusercontent.com/46487696/104123140-59eb4c00-536f-11eb-8e57-669b1090cef2.png)

Go to all jobs you will see a plus button click it. 

![Screenshot (1061)](https://user-images.githubusercontent.com/46487696/104124747-6b852180-5378-11eb-8f6d-8778d5483e2d.png)

Select Build Pipeline view and Give any name of your Pipeline you want > Click on ok and you will redirect to the configuration part.

Go to "Pipeline Flow" and Select Initial Job > Click okay 

![Screenshot (1062)](https://user-images.githubusercontent.com/46487696/104124784-9cfded00-5378-11eb-97dd-5d2e2d19d453.png)

You will be redirect to your pipeline view.

Green : done the execution, Blue : not started yet , Yellow: currently executing , Red : failed

![Screenshot (1063)](https://user-images.githubusercontent.com/46487696/104124852-1bf32580-5379-11eb-951f-88d29c60ad56.png)
![Screenshot (1065)](https://user-images.githubusercontent.com/46487696/104124854-1d245280-5379-11eb-89f0-d0f51409fc5a.png)

