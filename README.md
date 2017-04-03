# README

Steps for provisioning a VM to host the Jenkins CI Server:
1) Create Vagrant file to provision a virtual box to host the Jenkins CI server (available at 192.168.0.252)
2) Create ansible playbook and role for Jenkins using template (https://github.com/ICTO/ansible-jenkins) in the `infrastructure` folder
3) Create `ansible.host` file in the root of the repo to tell ansible where to find the host


Jenkins details:
username: admin
password: password


TODO: davidtan [2017-04-01]:
1) Jenkins setup for rails projects:
	- https://www.mobomo.com/2013/05/howto-install-setup-jenkins-ci-for-rails-projects/
	- https://gist.github.com/usrlocalts/1b923010896b9843dc80
2) Setting up Jenkins server with Ansible:
	- http://codeheaven.io/an-introduction-to-ansible/
3) https://vexxhost.com/resources/tutorials/how-to-install-configure-and-use-jenkins-on-ubuntu-14-04/
4) Run jenkins behind a reverse proxy:
	- https://wiki.jenkins-ci.org/display/JENKINS/Jenkins+behind+an+NGinX+reverse+proxy
	- http://www.yolinux.com/TUTORIALS/Jenkins.html
	- https://www.codeproject.com/Articles/1056410/Setup-Configure-Jenkins-For-Your-Team-in-Automated
5) install plugins:
	- https://wiki.jenkins-ci.org/display/JENKINS/Ruby+Plugin
6) Jenkins docs: https://jenkins.io/doc/
7) [not used] Setting Jenkins CI server on AWS: https://www.youtube.com/watch?v=zEQUuo5nWbo


Done:
1) Created application with tests
2) Created ubuntu box ('jenkins') and ssh-ed into it to install git, ruby, nginx, etc (see https://www.mobomo.com/2013/05/howto-install-setup-jenkins-ci-for-rails-projects/)
3) updated nginx config (`/etc/nginx/nginx.conf`):

```
http {          
	# ...Omitted Parts…          
	include /etc/nginx/conf.d/*.conf;    # This line not modified.         
	include /etc/nginx/sites-enabled/*;  # This line not modified.          
	##         
	# Reverse proxy port 80 to port 8080 for Jenkins         
	##         
	server {                 
		listen 80 default;                 
		server_name your.domain.com;                 
		location /{                         
			proxy_pass http://192.168.0.252:8080;                 
		}         
	}
}  

```
