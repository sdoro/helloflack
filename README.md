### Premessa

Nota: i commenti ('#') relativi al proxy vanno tolti se stiamo operando
dall'interno dell'Istituto Zuccante.


### Creazione 'in locale di' un progetto

	# export http_proxy="http://proxy.zuccante.it:8080/"
	# export https_proxy=$http_proxy
	mkdir helloflask && cd helloflask
	virtualenv venv
	source venv/bin/activate
	pip install Flask gunicorn
	nano hello.py
	nano Procfile
	foreman start

### Caricamento 'nel cloud' di un progetto

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

### Modififica 'in locale' di un progetto gia' esistente

	cd helloflask
	source venv/bin/activate
	foreman start

### Modifica 'nel cloud' di un progetto gia' esistente

	cd helloflask
	source venv/bin/activate
	nano 'some files'
	git add 'list of edited files'
	git commit -m "Some changes ...'
	git push heroku master

