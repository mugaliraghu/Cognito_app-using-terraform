## prerequisites

1.Python

2.AWS cli with configure.

## Steps:

Clone the Project and navigate to the folder "cognito-app" and run the below command.
```t
python -m http.server 
```
the code will run on the PORT 8000,open the Browser and run the Below url
```t
localhost:8000
```
you will get the output as shown in below image.


![Screenshot (95)](https://user-images.githubusercontent.com/120295902/235646615-444e1946-0323-4395-9fac-0d55266d13d6.png)

after that go to the terraform folder and navigate to the main file and run the command
```t
terraform init
```
then, use need to use the below command to validate the file
```t
terraform validate
```
and terraform plan will generate execution plan, showing you what actions will be taken without actuallay performing planned actions.
```t
terraform plan
```
after perform below command to deploy the application in aws and '--auto-approve' applying changes without having to interactively type 'yes' to the plan.
```t
terraform apply --auto-approve
```
to verify the resources, open the management console and go to the "cognito" search the name of the userpool that you given while creating terraform code, also check with the App integration in that it will create App clients, go inside that and you will find "Hosted Ui".

open the "view  Hosted UI" it will redirected to the website, copy that url and paste it inside the Cognito app files, replace # with url in index.html
as shown in below image

![Screenshot (100)](https://user-images.githubusercontent.com/120295902/235729317-90441b7e-8859-4a6b-b343-2aaae7b733e0.png)

and do same in logged_out.html(same url used for both index.html and logged_in.html).

![Screenshot (102)](https://user-images.githubusercontent.com/120295902/235729341-80a18471-a6dc-4690-90ca-606b7d86db81.png)

for logged_in.html do some changes in url, that is replace login with logout, logged_in with logged_out, redict_uri with logout_uri and remove response type and scope. As shown in below image.

![Screenshot (101)](https://user-images.githubusercontent.com/120295902/235729327-838b19c6-7737-4cdb-8edf-202f523a8126.png)

Now, Signup application with email and password, it will sent verification code to the email, after verification you will logged into application.
after logged in, check with the lambda function cloudwatch logs it will show the details of the user, that is as shown in image

![Screenshot (103)](https://user-images.githubusercontent.com/120295902/235731255-f7eea894-d373-4ef8-b87e-a023f79de472.png)

