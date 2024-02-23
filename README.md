You are asked to create a simple NodeJS app that lists all the projects each developer is working on. Everyone on your team wants to be able to see the list themselves and share with the project managers, so they ask you to make it available online, so everyone can access it.

</details>

******

<details>
<summary> Clone Git Repository </summary>
 <br />

For that you can use my provided git repository.

- clone the git repository and
- create your own project/git repo from it

**steps:**

```sh
# clone repository & change into project dir
git clone git@gitlab.com:twn-devops-bootcamp/latest/05-cloud/cloud-basics-exercises.git
cd cloud-basics-exercises.git

# remove remote repo reference and create your own local repository
rm -rf .git
git init 
git add .
git commit -m "initial commit"

# create git repository on Gitlab and push your newly created local repository to it
git remote add origin git@gitlab.com:{gitlab-user}/{gitlab-repo}.git
git push -u origin master

```

<img src="https://i.imgur.com/RQxAjmJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<img src="https://i.imgur.com/J7YKmN2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Package NodeJS App </summary>
 <br />

To have just 1 file, you create an artifact from the Node App. So you do the following:

- Package your Node app into a tar file (npm pack)

**steps**

```sh
cd app
npm pack

```

<img src="https://i.imgur.com/fD8DvKo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Create and prepare server on Digital Ocean </summary>
 <br />

Your company uses DigitalOcean as Infrastructure as a Service platform, instead of having on-premise servers. So you:

- Create a new droplet server on DigitalOcean


<img src="https://i.imgur.com/W1KYhKX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/V0V0ukL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/nN7rM7M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/2wCPkrx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Now you have a new fresh server nothing installed on it. Because you want to run a NodeJS application you need to install Node and npm on it:

- Install nodejs & npm on it

**steps:**
```sh
# ssh into your newly created server
ssh root@{server-ip-address}

# install nodejs and npm
apt install -y nodejs npm

```

<img src="https://i.imgur.com/qBJCDFM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/ol77Cdg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</details>

******

<details>
<summary> Copy App and package.json </summary>
 <br />

Having everything prepared for the application, you finally:

- Copy your simple Nodejs app to the droplet

**steps:**
```sh
# secure copy project file from local machine to server. Execute from project's root folder.
scp bootcamp-node-project-1.0.0.tgz root@{server-ip-address}:/root

```


<img src="https://i.imgur.com/tYVbhDK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

<details>
<summary> Run Node App </summary>
 <br />

Start the node application in detached mode (npm install and node server.js commands)

**steps:**
```sh
# ssh into droplet
ssh -i ~/id_rsa root@{server-ip-address}

# unpack the node-project file
tar -zxvf bootcamp-node-project-1.0.0.tgz

# change into unpacked directory called "package"
cd package

# install dependencies
npm install

# run the application
node server.js

```

<img src="https://i.imgur.com/eIu7Rtr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</details>

******
