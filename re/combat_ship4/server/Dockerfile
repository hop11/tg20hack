FROM ubuntu:xenial

RUN apt update && apt install -y xinetd
RUN useradd -m -s /bin/bash tghack

COPY re_noob4 /home/tghack/re_noob4
RUN chmod 765 /home/tghack/re_noob4

COPY flag.txt /home/tghack/flag.txt
RUN chmod 644 /home/tghack/flag.txt

COPY re_noob4.xinetd /etc/xinetd.d/re_noob4
RUN chmod 644 /etc/xinetd.d/re_noob4
RUN chown -R root:root /home/tghack

COPY wrap.sh /opt/wrap.sh
RUN chmod 755 /opt/wrap.sh

RUN chmod 1770 /tmp
RUN chown -R root:root /home/tghack

CMD service xinetd start && /bin/bash
