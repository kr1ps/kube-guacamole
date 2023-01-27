# kube-guacamole# Apache guacamole

This chart its a fork fodified to work on latest k8s version from this repo https://github.com/halkeye-helm-charts/guacamole.

This helm chart provides a complete setup of:

- Guacamole server
- Guacd Proxy


Requirement:

- postgresql database
- database <database_name> created
- login with md5 password encript

Postgresql query to modify an user to change encryption to md5

```SHOW password_encryption;
SELECT rolpassword from pg_authid where rolname = 'guacadmin';
SET password_encryption  = 'md5';
ALTER USER "guacadmin" with password 'password';```


You can get it up ang running by:

1. git clone https://github.com/kr1ps/kube-guacamole.git
2. cd helm
3. helm install . -f values.yaml --name=guacamole --namespace=guacamole
5. visit http://guacamole.yourdomain.com in your browser. Default creds are guacadmin/guacadmin
