# CBRAIN Bourreau installation

## On Bourreau host

1. Install Ruby

**As root**

```bash
dnf install -y perl libffi-devel readline-devel ruby sqlite-devel libsodium libsodium-devel mysql mysql-devel
dnf group install -y "Development Tools"
```

**As standard user**

Install openssl 1.1.1w
```bash
# Install openssl 1.1.1w
mkdir ~/.local

cd /tmp/
curl -o openssl-1.1.1w.tar.gz  https://ftp.openssl.org/source/old/1.1.1/openssl-1.1.1w.tar.gz
tar -xzvf openssl-1.1.1w.tar.gz

cd /tmp/openssl-1.1.1w
./config --prefix=/home/cbrain/.local/openssl-1.1w
make
make install

# fix libaries path and ssl certifcate
cd ~/.local/openssl-1.1w/
ln -s lib lib64
ln -s libcrypto.so.1.1 libcrypto.so.10
ln -s libssl.so.1.1 libssl.so.10
cd ssl/
ln -s /etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem cert.pem

 # Export env
export LD_LIBRARY_PATH="/home/cbrain/.local/openssl-1.1w/lib"
export PATH="/home/cbrain/.local/openssl-1.1w/bin:${PATH}"
 ```

Install rvm
```bash
gpg2 --keyserver hkp://keyserver.ubuntu.com --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash -s stable
echo 'source $HOME/.rvm/scripts/rvm' >> ~/.bash_profile
source ~/.bash_profile
 ```

Install ruby
```bash
rvm install 2.7 --with-openssl-dir=$HOME/.local/openssl-1.1w
rvm install 2.7-head --with-openssl-dir=$HOME/.local/openssl-1.1w
rvm use 2.7-head --default
 ```

2. Install the Bourreau

```
# Install the Bourreau
git clone https://github.com/aces/cbrain.git
cd cbrain/Bourreau/
bundle install
bundle exec rake cbrain:plugins:install:all



# Modify the config file
cd /home/cbrain/cbrain/Bourreau
cp config/initializers/config_bourreau.rb.TEMPLATE config/initializers/config_bourreau.rb

# l.44 to be modified with the name setup in CBRAIN UI `bourreau_hostname` in UI example
vi  config/initializers/config_bourreau.rb



# Create a directory for the caches
mkdir /path/to/dp/caches

# Create a directory for the shared work directory
mkdir /path/to/shared/directory
 ```

## In CBRAIN UI

**Note**: Make sure to have the `/path/to/dp/caches`  and the `/path/to/shared/directory` setup of bourreau host.

Go to the `Servers` tab then click on `Create New Server`.

Then fill the form as indicated here:

1. General setup:

[[setup-guide/images/01_SetupRocky.png]]

2. Configure the cache
[[setup-guide/images/02_SetupRocky.png]]

3. Configure the Cluster Management system
[[setup-guide/images/03_SetupRocky.png]]


