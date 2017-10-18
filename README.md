# empirelogistics

In order to avoid a catch-22 when your server is brand new, here is some external bootstrapping or help in order to get started.  Copy the following block of lines and paste it into the shell.

-------------------------------------------------------------------------------------------------------------------------

sed -i 's/#precedence\ ::ffff:0:0\\\/96\ \ 100/precedence\ ::ffff:0:0\\\/96\ \ 100/' /etc/gai.conf;sed -i 's/#prefer-family = IPv6/prefer-family = IPv4/' /etc/wgetrc;apt install -y zip unzip fail2ban;wget https://raw.githubusercontent.com/empirelogistics/empirelogistics/master/howto_latest.zip;unzip howto_latest.zip

-------------------------------------------------------------------------------------------------------------------------

If you want to know what these lines do, read on.

What does it do?

We are going to use the package manager 'apt' to download other projects and files.  The downloader follows rules about the precedence between IP addresses in the old format (IPv4) and IP addresses in the new format (IPv6).  This may lead to a 
logjam if the one marked "give precedence to this kind" is not available, blocking any progress at all.  The first two lines make a change in precedence to avoid this.  The third line calls the package manager.  'zip' and 'unzip' are for compression.  'fail2ban' is one of our security measures.  The fourth line downloads a bundle of files that we will use to build the map server itself so that we can get on to subject matter more quickly.  The fifth line uncompresses this code.

