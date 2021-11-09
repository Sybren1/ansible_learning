# ansible_learning
Met deze repo ga ik leren hoe ik ansible ga gebruiken en leren
Alles is getest op linux machines
Voor het gebruik van deze playbooks bootstrap, site, install_apache en remove_apache.
Moet je ansible op je main machine hebben gedownload.
De inventory staan hosts ip adressen, zorg ervoor dat deze ip adressen kloppen  met de machines die jij gebruikt.
Ik heb ook gebruik gemaakt van hele simpele wachtwoorden, als je goed kijkt hebben we een main account toegevoegd die de juiste SSH keys gebruikt om in te loggen met de machines.
Tijdens het testen heb ik de dezelfde wachtwoorden gebruikt voor elke verschillende hosts, omdat dit makkelijker was voor het uitvoeren van de Paybooks.
Gebruikers naam en Wachtwoord voor de ansible machine is: ansible
# SSH
Ansible maakt gebruik van ssh keys om een connectie te maken met de hosts machines.
In mijn voorbeeld heb ik gebruik gemaakt van de commandos hieronder

ssh-keygen -t ed25519 -C "[key-name]"

Zorg ervoor dat je geen passprases gebruikt, anders kan ansible niet gebruik maken van je key

Kijk uit dat als je de key file naar id_ed25519 noemt je niet nog een key aanmaakt met dezelfde naam. Anders overite je de key. De key naam die ik gebruikt heb is ansible

ssh-copy-id -i  ~/.ssh/ansible [hosts ip adress]

Check of je zonder wachtwoord een ssh connectie kunt maken

ssh -i ~/.ssh/ansible [hosts ip adress]
