# Kannel
Les configurations de kannel (gateway)

#install kannel
sudo apt-get install kannel

#install extras
sudo apt-get install kannel-extras

#install lib
sudo apt-get install libxml2
sudo apt-get install gcc

#Replace your default kannel.conf by the file that I commited:
#default kannel.conf is save in /etc/kannel/kannel.conf
#open 'kannel.conf'
sudo gedit /etc/kannel/kannel.conf

#change 'my-nuber' by the number of the sim card
#it's the line 49

#copy the file 'modems.conf' to '/etc/kannel/'
sudo cp /usr/share/doc/kannel/examples/modems.conf /etc/kannel/

#stop kannel
sudo service kannel stop

#start bearerbox
sudo bearerbox -v 0 /etc/kannel/kannel.conf

#open a new terminal
#start smsbox
sudo smsbox -v 0 /etc/kannel/kannel.conf

#now you can send sms from your pc
#open your browser, type the following URL:
http://localhost:13013/cgi-bin/sendsms?username=rapidsms&password=CHANGE-ME&to=+509********&text=testSMS&from=+509********
