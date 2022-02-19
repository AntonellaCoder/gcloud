# Google Cloud Configuration

This guide is to create a micro instance for free or a minimun cost, using Ubuntu 20 LTS.
The type of instance is First Generation N1, located in North Carolina.
Boot disk of 20GB, Standart persistant storage. Allow HTTP and HTTPS.

## Connecting the instance

Install gcloud according to this webpage in your local computer.

https://cloud.google.com/sdk/docs/install-sdk?hl=en_US

Download the file.tar.gz and move it to home directory in your local pc.

```mv ~/Download/examplefile.tar.gz ~/```

```cd ~```

Extract the examplefile.tar.gz

```tar -xvzf examplefile.targ.gz```

Install it, if located in your hombe run this.

```./google-cloud-sdk/install.sh```

Initialize the gcloud.

```./google-cloud-sdk/bin/gcloud init```

In your instance webpage go to Connect and select view gcloud command.

Copy and paste it on your terminal to connect to the instance.

Updating and upgrading

``` sudo apt update && upgrade ```

## Optimizing the instance by adding swap file.

See if you have file swap with htop

```htop```

Create the swapfile

```sudo fallocate -l 1G /swapfile```

Wipe the file out

```sudo dd if=/dev/zero of=/swapfile bs=1024 count=1048576```

Give it root privileges.

```sudo chmod 600 /swapfile```

Make the swapfile

```sudo mkswap /swapfile```

Turn on the swapfile

```sudo swapon /swapfile```

Open this file with vim or nano

```sudo vim /etc/fstab```

Add this line to the file mentioned before

```/swapfile swap swap defaults 0 0```

Run this command to see if any errors.

```sudo mount -a```

Verified that you have the swapfile running.

```htop```

Get my static ip

```curl ifconfig.me```


