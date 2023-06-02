# Tema 3

## Implement user authentication and authorization

*1.-* ¿Qué es la Plataforma de Identidad de Microsoft y cómo se utiliza para la autenticación de usuarios?

    La Plataforma de Identidad de Microsoft es un conjunto de tecnologías y servicios que permiten a los usuarios autenticarse y acceder a los recursos de Microsoft y de terceros de manera segura y confiable.

    La autenticación de usuarios, la Plataforma de Identidad de Microsoft utiliza diferentes métodos, como la autenticación multifactor, la autenticación basada en certificados y la autenticación biométrica.

*2.-* ¿Cuál es el flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft?

    El flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft es el flujo de autenticación basado en OAuth 2.0 y OpenID Connect. 
    Este flujo permite a los usuarios autenticarse en una aplicación o sitio web utilizando sus credenciales de Microsoft.

*3.-* ¿Cómo se obtienen y se utilizan los tokens de acceso para autorizar solicitudes a recursos protegidos?

    Los tokens de acceso se obtienen mediante un proceso de autenticación y autorización del usuario. Una vez que el usuario ha sido autenticado y autorizado para acceder a un recurso protegido, se le otorga un token de acceso que contiene información sobre su identidad y permisos de acceso.

    Permite o denega el acceso en función de los permisos que se hayan otorgado al usuario

## Preguntas 

*1.-* Your company is developing an Azure API.
You need to implement authentication for the Azure API. You have the following requirements:

All API calls must be secure.

Callers to the API must not send credentials to the API.


Which authentication mechanism should you use?

    A. Basic

    B. Anonymous

    C. Managed identity

    D. Client certificate

    Correct Answer: C

    Explanation:

    Use the authentication-managed-identity policy to authenticate with a backend service using the managed
    identity of the API Management service. This policy essentially uses the managed identity to obtain an
    access token from Azure Active Directory for accessing the specified resource. After successfully obtaining
    the token, the policy will set the value of the token in the Authorization header using the Bearer scheme.

*2.-* You are developing a website that will run as an Azure Web App. Users will authenticate by using their Azure Active Directory (Azure AD) credentials.

You plan to assign users one of the following permission levels for the website: admin, normal, and reader.A user’s Azure AD group membership must be used to determine the permission level. You need to configure authorization.

Solution: Configure the Azure Web App for the website to allow only authenticated requests and require Azure AD log on.

Does the solution meet the goal?

    A. Yes

    B. No

    Correct Answer: B

    Explanation:
    Instead in the Azure AD application’s manifest, set value of the groupMembershipClaims option to All.

*3.-* You are developing a website that will run as an Azure Web App. Users will authenticate by using their Azure Active Directory (Azure AD) credentials.
You plan to assign users one of the following permission levels for the website: admin, normal, and reader. A user’s Azure AD group membership must be used to determine the permission level.

You need to configure authorization.

Solution:

Create a new Azure AD application. In the application’s manifest, define application roles that match the required permission levels for the application.
Assign the appropriate Azure AD group to each role. In the website, use the value of the roles claim from the JWT for the user to determine permissions.

Does the solution meet the goal?

    A. Yes

    B. No

    Correct Answer: B

    Explanation:
    To configure Manifest to include Group Claims in Auth Token
    1. Go to Azure Active Directory to configure the Manifest. Click on Azure Active Directory, and go to App
    registrations to find your application:
    1. Click on your application (or search for it if you have a lot of apps) and edit the Manifest by clicking on it.
    2. Locate the “groupMembershipClaims” setting. Set its value to either “SecurityGroup” or “All”. To help
    you decide which:
    “SecurityGroup” - groups claim will contain the identifiers of all security groups of which the user is a member.
    “All” - groups claim will contain the identifiers of all security groups and all distribution lists of which the user is a member
    Now your application will include group claims in your manifest and you can use this fact in your code.