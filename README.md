# Heimdall
It's a tool to manage vulnerables packages in your *nix server, in a centralized way

#How to install
git clone https://github.com/mthbernardes/heimdall_webserver.git
cd heimdall_webserver
chmod +x install.sh
./install.sh
python manage.py runserver 0.0.0.0:1337
The default credentials are 
heimdall:heimdall (CHANGE THAT)

#How it works
1. Install and configure the Heimdall web platform(heimdall_webserver) on a server where you will manage all your other clients(servers)
2. Install and configure the Heimdall agent on your clients(<a href="https://github.com/mthbernardes/heimdall_agent">heimdall_agent</a>)
3. The client get all packages installed and consult on <a href="https://vulners.com">vulners.com</a>, to find wich package is vulnerable.
4. The client report the vulnerables packages to heimdall_webserver
5. Now you can upgrade the packages in all your server using just the Heimdall Web Platform

#Groups privilegies
admin - Can do everything
infra - Just can't create users
security,dev - Can only see informations about the servers

#How to register a client
got to http://localhost:1337/cliente/cadastrar
First insert the client name (just to know what server is, this information is not used in anyway)
Set the server ip addres and the client port, the defaul port is 5000
Select the distro
Click in register
It's done

#How upgrade the packages
After you have installed the packages on your client, it start to communicate with the server, and send the vulnerable packages, so when a vulnerable package appear, just click in update.
after the upgrade finish, you can see the upgrade response, clicking on view.
It's done
