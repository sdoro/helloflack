	# export http_proxy="http://proxy.zuccante.it:8080/"
	# export https_proxy=$http_proxy
	heroku login
	mkdir helloflask
	cd helloflask
	virtualenv venv
	source venv/bin/activate
	pip install Flask gunicorn
	nano hello.py
	nano Procfile
	foreman start
	pip freeze > requirements.txt
	cat requirements.txt 
	nano .gitignore
	git init
	git add .
	git commit -m "init"
	heroku create
	git push heroku master
	ssh-keygen -f ~/.ssh/id_rsa_netkit -C "knoppix@netkit.org-$(date -I)"
	heroku keys:add /home/knoppix/.ssh/id_rsa_netkit.pub
	git push heroku master
	pip install distribute -U
	pip freeze > requirements.txt
	git commit -m "init" requirements.txt
	git push heroku master
