# Mini Project Assignment for Ansible playbook on `httpd`

## Mini-Project instruction and steps
```
Write code in a programming language (or languages, configuration management platforms,
etc.) of your choice that provisions an environment in AWS. The infrastructure code only needs
to provision the environment resources and configure a web server. The home page should
display a static HTML page with the words: “Automation for the People” .

Requirements:
- AWS must be the target infrastructure.
- Single Command/One-Click launch of environment.
  - Some prerequisites are OK as long as it is properly documented.
- Commit all code to the private repository that is provided for you in Github.
- Include a README.MD containing detailed directions on how to run, what is running, and how to cleanup.
- Include some form of automated tests. Demonstrate a test-first mentality.

```

# Git clone the repo on any Linux Platform
```
git clone https://github.com/donekudison/Stack-app.git
```
# Follow these steps to [paired keys](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html) if no keys are created or paired
```
 To log in to your instance, you must create a key pair, specify the name of the key pair when you launch the instance,
 and provide the private key when you connect to the instance.
 On a Linux instance, place your public key content in an entry within ~/.ssh/authorized_keys.

```
# A simple Ansible playbook to provision the environment resources and configure a web server for RHEL/CentOS 7 on AWS-Instance and do cleanup if needed.

```
      Requirements before running this playbook.

- Run with a user who have sudoer  privileges
- Also add instance group into the inventory file

```
# Change Directory to the project directory

```
$ cd project-MyName
```
# To Lunch Environment, run the below command
```
$ ansible-playbook -i inventory app-builder/webserver.yml --sudo

```
# Activity of the playbook

```
- Install the necessary packages;
- Maintain the main configuration file;

```
#  How to cleanup. `In the same directory`, Run the below command

```
$ ansible-playbook -i inventory cleanup/clean-play.yml --sudo

```

## Requirements
```
HTTPS/TLS is enabled, by default using the standard self-signed certificate.
You can provide your own certificate by setting the appropriate role variables.
```

## Secure web Variables

Applying this playbook role will result in a configuration equivalent to installing a web server. 

| Variable                        | Default                                                                                 
| :---                            | :---                                                                                                                      
| `httpd_AccessLog_ssl`           | logs/ssl_access_log                                                                                                             
| `httpd_DocumentRoot`            | '/var/www/html'                                                                                                                   
| `httpd_ErrorLog_ssl`            | logs/ssl_error_log                                                                                                                
| `httpd_ErrorLog`                | logs/error_log                                                                                                                    
| `httpd_Listen_ssl`              | 443                                                                                                                               
| `httpd_Listen`                  | 80                                                                                                                                
| `httpd_LogLevel_ssl`            | warn                                                                                                                              
| `httpd_LogLevel`                | warn                                                                                                                              
| `httpd_SSLCACertificateFile`    | -                                                                                                                                 
| `httpd_SSLCertificateChainFile` | -                                                                                                                                 
| `httpd_SSLCertificateFile`      | /etc/pki/tls/certs/localhost.crt                                                                                                  
| `httpd_SSLCertificateKeyFile`   | /etc/pki/tls/private/localhost.key                                                                                              
| `httpd_SSLCipherSuite`          |                                                                                       
| `httpd_SSLHonorCipherOrder`     | 'on'                                                                                                                             
| `httpd_SSLProtocol`             | 'all -SSLv3 -TLSv1'                                                                                                               
| `httpd_ServerAdmin`             | root@localhost                                                                                                                  
| 'httpd_ServerRoot'              | '/etc/httpd'                                                                                                                      
| 'httpd_ServerTokens'            | web                                        
| 'httpd_DirectoryIndex'          | index.html                      

## Liences
```
None
```


