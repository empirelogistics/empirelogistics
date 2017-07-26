# empirelogistics

It's possible to have a catch-22 situation very early in the build.  We have to download and install some things in order
to get started, but these downloads may hang because IPv6 has precedence over IPv4.  If the very first downloads do not work,
copy the following and paste it into the shell

## edit /etc/gai.conf to prioritize IPv4 when contacting repos

sed -i 's/#precedence\ ::ffff:0:0\/96\ \ 100/precedence\ ::ffff:0:0\/96\ \ 100/' /etc/gai.conf

## edit /etc/wgetrc to prioritize IPv4 when downloading with wget

sed -i 's/#prefer-family \= IPv6/prefer-family = IPv4/' /etc/wgetrc

