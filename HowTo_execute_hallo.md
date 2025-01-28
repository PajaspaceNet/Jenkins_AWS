
# Strucny postup neuplny postup
Předpoklady
```
Jenkins je již nainstalovaný a běží - popis instalace v dockeru nize
Máte repozitář na GitHubu.
Git Plugin a GitHub Integration Plugin jsou nainstalované v Jenkinsu - popis nize
GitHub token je k dispozici (pro přístup do repozitáře).
```
1/
** V AWS ve vytvorene instanci ,se konektem do konzole **
Docker official GPG key:
```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
#Pridani repo to Apt sources:
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
odemkmneme a prihlasime se do Jenkins
   
2. Nastavte projekt v Jenkinsu

    Vytvořte nový projekt:
   ```
        V Jenkinsu klikněte na New Item a zvolte Freestyle project.
       Zadejte název projektu (např. RunHelloScript) a klikněte na OK.
   ```

    Source Code Management (SCM):
```
    Vyberte Git.
        Zadejte URL vašeho repozitáře (např. https://github.com/<username>/<repo>.git).
        Pokud je repozitář soukromý, přidejte přihlašovací údaje.
```

    Build krok pro spuštění skriptu:
  
        Přejděte na Build > Add build step > Execute shell.
        Zadejte následující příkaz:
   
    ```
        chmod +x hello.sh
        ./hello.sh
```
    Klikněte na Save.
```
4. Spusťte build

```
    Klikněte na Build Now v Jenkinsu.
    Přejděte na probíhající build a otevřete Console Output.
```
5. Co byste měli vidět v Console Output

Pokud je vše správně nastaveno, uvidíte ve výstupu:
```
Hello from Jenkins!
```
