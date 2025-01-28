## Strucny postup neuplny postup 

# Předpoklady

    Jenkins je již nainstalovaný a běží. -  popis instalace v dockeru nize
    Máte repozitář na GitHubu.
    Git Plugin a GitHub Integration Plugin jsou nainstalované v Jenkinsu.
    GitHub token je k dispozici (pro přístup do repozitáře).

 ** V AWS ve vytvorene instanci ,se konektem do konzole ** 

# Docker official GPG key:
```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
# Pridani repo  to Apt sources:
```
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```
sudo apt-get update
```

#instalace dockeru
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#test dockeru 
```
sudo docker run hello-world
```

#instalace Jenkins 
```
sudo docker run -p 8080:8080 -p 50000:50000 -v /home/ubuntu:/var/jenkins_home jenkins/jenkins
```
nastavenime outbound rules v AWS 


# odemkmneme a prihlasime se do Jenkins 
 

# Nastavime Jenkins projekt

* a. Vytvořte nový Jenkins projekt:
```
    Otevřete Jenkins.
    Klikněte na New Item.
    Zadejte název projektu (např. UpdateGitHubMessage).
    Vyberte Freestyle project a klikněte na OK.
```
* b. Konfigurace projektu:


Klikněte na Add build step > Execute shell.
Vložte následující příkaz:
```
echo "hello from jenkins" > message.txt
git config --global user.name "Jenkins Bot"
git config --global user.email "jenkins-bot@example.com"
git add message.txt
git commit -m "Update message from Jenkins"
git push origin main
```
# Vytvorete si na gitu 
ve svem repu soubour  message.txt
s textem jakym chcete nebo prazdny.
  
   # Manuální build:
        Klikněte na Build Now v Jenkinsu.
   # Ověřte změny na GitHubu:
        Otevřete repozitář na GitHubu.
        Zkontrolujte obsah souboru message.txt, který by měl být aktualizován na:
```
hello from jenkins
```

# TO DO:: 
Muzume dale aplikovat Webhooky.


   






