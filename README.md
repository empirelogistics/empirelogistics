# empirelogistics

It's possible to have a catch-22 situation very early in the build.  We have to download and install some things in order
to get started, but these downloads may hang because IPv6 has precedence over IPv4.  If the very first downloads do not work,
copy the following and paste it into the shell

sed -i 's/#precedence\ ::ffff:0:0\/96\ \ 100/precedence\ ::ffff:0:0\/96\ \ 100/' /etc/gai.conf

sed -i 's/#prefer-family \= IPv6/prefer-family = IPv4/' /etc/wgetrc

# Now you can carry on to the lines given in the guide:

apt install zip unzip fail2ban

wget [the latest zip such as howto_latest.zip]

unzip [that zip file]

./script.sh
.
.
.
