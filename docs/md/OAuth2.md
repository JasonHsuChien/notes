#### OAuth defines four roles –

- **Resource Owner** – The user of the application.
- **Client** – the application (user is using) which require access to user data on the resource server.
- **Resource Server** – store user’s data and http services which can return user data to authenticated clients.
- **Authorization Server** – responsible for authenticating user’s identity and gives an authorization token. This token is accepted by resource server and validate your identity.

OAuth 2.0的运行流程如下图

![img](https:////upload-images.jianshu.io/upload_images/15209061-98feec3dbfd354bf.png?imageMogr2/auto-orient/strip|imageView2/2/w/766/format/webp)

#### OAuth运行流程

> （A）用户打开客户端以后，客户端要求用户给予授权。
>  （B）用户同意给予客户端授权。
>  （C）客户端使用上一步获得的授权，向认证服务器申请令牌。
>  （D）认证服务器对客户端进行认证以后，确认无误，同意发放令牌。
>  （E）客户端使用令牌，向资源服务器申请获取资源。
>  （F）资源服务器确认令牌无误，同意向客户端开放资源。

#### Access Token vs Refresh Token

An **access token** is a string representing an authorization issued to the client. Tokens represent specific scopes and durations of access, granted by the resource owner, and enforced by the resource server and authorization server.

**Refresh token** is issued (along with access token) to the client by the authorization server, and it is used to obtain a new access token when the current access token becomes invalid or expires. The refresh token is also used to get additional access tokens with identical or narrower scope (access tokens may have a shorter lifetime and fewer permissions than authorized by the resource owner). Issuing a refresh token is optional at the discretion of the authorization server.

- The responsibility of access token is to access data before it gets expired.
- The responsibility of refresh token is to request for a new access token when the existing access token is expired.



https://www.jianshu.com/p/84a4b4a1e833

https://howtodoinjava.com/spring-boot2/oauth2-auth-server/

