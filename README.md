# aws-elasticbeanstalk-troubleshooting

I got today issue with AWS Elasticbeanstalk with this error `413 Request Entity Too Large`

## Solution

* Create folder `.ebextensions/`
* create file `.ebextensions/nginx.config`
* nginx.config has this content 

```
  "/etc/nginx/conf.d/proxy.conf" :
  mode: "000755"
  owner: root
  group: root
  content: |
       client_max_body_size 500M;

```
