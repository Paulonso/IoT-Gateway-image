# IoT-Gateway-image
OpenEmbedded Development Tree

#IoT gateway image
#Gateway with SMB, ssh and dnsmasqs

SPLASH ?= ' ${@base_contains("MACHINE_FEATURES", "screen", "psplash-gateway", "",d)}'

GATEWAY_EXTRA_INSTALL ?= ""
DISTRO_SSH_DAEMON ?= "dropbear"

IMAGE_INSTALL = "task-boot \
            ${DISTRO_SSH_DAEMON} \
            iptables \
            samba swat \
            dnsmasq \
#            vsftpd \
            gateway-version \
            ${SPLASH} \
	   "

export IMAGE_BASENAME = "gateway-image"
IMAGE_LANGUAGES = ""

inherit image
