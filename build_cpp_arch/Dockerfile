FROM base/archlinux

# Set proxy server, replace host:port with values for your servers
#ENV http_proxy localhost:3128
#ENV https_proxy localhost:3128

RUN curl -o /etc/pacman.d/mirrorlist "https://www.archlinux.org/mirrorlist/?country=all&protocol=https&ip_version=6&use_mirror_status=on" && sed -i 's/^#//' /etc/pacman.d/mirrorlist

RUN pacman-key --refresh-keys && \
  pacman --sync --refresh --noconfirm --noprogressbar --quiet && \
  pacman --sync --noconfirm --noprogressbar --quiet archlinux-keyring openssl pacman && \
  pacman-db-upgrade && \
  pacman --sync --sysupgrade --noconfirm --noprogressbar --quiet && \
  pacman --sync --noconfirm --noprogressbar --quiet base-devel git namcap
