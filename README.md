## Command to run:
```
git clone https://github.com/ykbryan/aws-cognito-dotnet-reactjs-app
cd aws-cognito-dotnet-reactjs-app
dotnet run watch
```

## Setup reference
dotnet new react -o my-new-app
https://docs.microsoft.com/en-us/aspnet/core/client-side/spa/react?view=aspnetcore-6.0&tabs=visual-studio

dotnet run watch

### packages to install
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
dotnet add package System.IdentityModel.Tokens.Jwt

use postman to make api call to e.g. https://localhost:7049/weatherforecast
it should be HTTP ERROR 401 without any auth setup

## Postman 101
Token Name: any
Grant Type: implicit
Callback URL: http://localhost 
Auth URL: htts://mydomain.auth.xxxxxxx.cognitolongurl.com/login // this can found under Cognito User Pool / App Integration / Domain Name. And rem to add /login at the back
Client ID: xxx // Under Cognito User Pool / General Settings / App clients
Scope: (optional) // but if u did add scope to ur token. it is under under App Integration / Resource servers and must include the resource server ID (e.g. https://myresource.com/myscope)


then click [Get Access Token]

u see a AWS Cognito default sign in popup > login as usual

Postman redirects u back and u should be under Manage Access Tokens
click [use Token]

Now go back to your usual Postman workflow and click "SEND"

## References
https://dev.to/packt/creating-spas-using-asp-net-core-and-react-59a0
https://stackoverflow.com/questions/52287506/how-do-i-integrate-amazon-cognito-login-in-postman#answer-53018712
https://github.com/lopezlucas/IDaaS-Example