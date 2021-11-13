### ldap_user_provider

```
request.INFO: Matched route "login_ldap". {"route":"login_ldap","route_parameters":{"_route":"login_ldap","_controller":"App\\Controller\\LoginLdapController::index"},"request_uri":"http://mup.test/login/ldap","method":"POST"} []
security.INFO: User has been authenticated successfully. {"username":"user01"} []
security.DEBUG: Stored the security token in the session. {"key":"_security_main"} []

request.INFO: Matched route "index". {"route":"index","route_parameters":{"_route":"index","_controller":"App\\Controller\\LoginController::index"},"method":"GET"} []
security.DEBUG: Read existing security token from the session. {"key":"_security_main","token_class":"Symfony\\Component\\Security\\Core\\Authentication\\Token\\UsernamePasswordToken"} []
security.DEBUG: User was reloaded from a user provider. {"provider":"Symfony\\Component\\Ldap\\Security\\LdapUserProvider","username":"user01"} []
security.DEBUG: Stored the security token in the session. {"key":"_security_main"} []
```

### app_user_provider

```
request.INFO: Matched route "login_ldap". {"route":"login_ldap","route_parameters":{"_route":"login_ldap","_controller":"App\\Controller\\LoginLdapController::index"},"request_uri":"http://mup.test/login/ldap","method":"POST"} []
doctrine.DEBUG: SELECT t0.id AS id_1, t0.email AS email_2, t0.roles AS roles_3, t0.password AS password_4 FROM `user` t0 WHERE t0.email = ? LIMIT 1 ["user@example.org"] []
security.INFO: User has been authenticated successfully. {"username":"user@mail.org"} []
security.DEBUG: Stored the security token in the session. {"key":"_security_main"} []

request.INFO: Matched route "index". {"route":"index","route_parameters":{"_route":"index","_controller":"App\\Controller\\LoginController::index"},"method":"GET"} []
security.DEBUG: Read existing security token from the session. {"key":"_security_main","token_class":"Symfony\\Component\\Security\\Core\\Authentication\\Token\\UsernamePasswordToken"} []
doctrine.DEBUG: SELECT t0.id AS id_1, t0.email AS email_2, t0.roles AS roles_3, t0.password AS password_4 FROM `user` t0 WHERE t0.id = ? [1] []
security.DEBUG: User was reloaded from a user provider. {"provider":"Symfony\\Bridge\\Doctrine\\Security\\User\\EntityUserProvider","username":"user@example.org"} []
security.DEBUG: Stored the security token in the session. {"key":"_security_main"} []
```
