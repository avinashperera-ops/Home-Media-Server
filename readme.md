<h1 align="center">How to build a Home Media Server from scratch!!</h1>

<h3>Enjoy all your favourite movies without having a SUBSCRIPTION!!</h3>

## All you need

- An old laptop or a PC with a Linux flavour of your choice installed. For my project I used Ubuntu server version. It's fully optimized for running servers.

- A media server service of your choice. For my project I used Jellyfin media server. It's free and easy to configure.

- Finally, A **GOOD INTERNET CONNECTION**. Seriously guys for this to work you should have to have a good internet connection.

## How to install

<h1>Step 1: Add Jellyfin GPG Key</h1>

Before adding the Jellyfin repository add its GPG key that will confirm the packages we are getting to install on our system are from the authentic source.

To get packages via a secure protocol, first enable its support using the below command:
$`sudo apt install apt-transport-https`</p>

<h2>Add key:</h2>

`wget -O - https://repo.jellyfin.org/jellyfin_team.gpg.key | sudo apt-key add -`

<h1>Step 2: Add Repository</h1>

Now, let’s add the Jellyfin repository as per the Debian or Ubuntu-based Linux system you are suing. This is a single command, thus you have to copy and paste it whole.`echo "deb [arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/$( awk -F'=' '/^ID=/{ print $NF }' /etc/os-release ) $( awk -F'=' '/^VERSION_CODENAME=/{ print $NF }' /etc/os-release ) main" | sudo tee /etc/apt/sources.list.d/jellyfin.list`

<h1>Step 3: Run system update</h1>

Rebuild the system’s repo cache, so that it could recognize the added repo and its corresponding packages to install on our system to set up the Jellyfin media server.`sudo apt update`

<h1>Step 4: Command to install Jellyfin</h1>

Finally, run the below command to automatically install Jellyfin on your Debian or Ubuntu-based Linux operating system you are using,`sudo apt install jellyfin`

<h1> Step 5: Enable and start Jellyfin server</h1>

Once the installation is completed, let’s start the Jellyfin Media server service on Ubuntu or Debian and enable the same, so that it could automatically get started with system boot.`sudo systemctl enable jellyfin`
`sudo systemctl start jellyfin`

You can also check whether everything is running properly or not by using :`sudo systemctl status jellyfin`

To exit simply press **Ctrl + C**.

<h1>Step 6: Setup and configure the Jellyfin media server</h1>

As everything is in position, our open-source media server is up and running, thus it is time to let’s access the Jellyfin web interface using the browser. If you are using a command-line server to set it up, then use some other local machine available to access the remote server where you have installed the Jellyfin.

In the browser, type the IP address of the server where Jellyfin has been installed along with port number **8096**. Whereas if you are using the Jellyfin installed server in GUI with browser access then we can use localhost or 127.0.0.1.

**Example**

`127.0.0.1:8096`

Or

`[IP_ADDRESS]:8096`

**Note**: Replace the IP address with your server address.

You will get the welcome screen to set up Jellfin further.

<h1>Step 7: Set Username and Password</h1>

Click on the **Next** button to start the Jellyfin media server setup. The next screen will appear for setting up the username and password for Admin that will have all the access to add/remove content and other settings.

<h1>Step 8: Add Library</h1>

Click on the **+** button, first select the category type, for media content files such as music, videos, and images and then type the path of the folder where you have to save the media you want to play on Jellyfin. For example, I have selected the Music category and then entered the path of the folder where I have saved my music files.

You can add multiple folders to your library right here or after whenever you want.

In case you want to use a smartphone and other devices to remotely connect Jellyfin using the internet then enable the “Allow remote connections to this Jellyfin Server” option. However, to access the server residing behind a local router and using a local IP address, to access it via the internet, the user has to forward its Jellyfin port manually.

<h1>Step 9: Login Jellyfin Server</h1>

Enter the username and password to log in, and then you will have the Interface of Jellyfin in your browser to access the music, videos, and other media files.

In case you want to add some more Library or media folders in Jellyfin, then go to Dashboard, select libraries, and then **“Add Media library”.**

Options to **restart** and **shut down** the server are also present under **Dashboard**.

<h1>Jellyfin Clients</h1>

This open-source media server supports multiple client applications to stream music and videos from the server. Thus, for the same, we can download **Jellyfin Client** as per our devices such as Firestick, Android TV, iPhone, Kodi, Roku, and more…

Download Jellyfin 

<a href="https://jellyfin.org/">Download Jellyfin</a>
