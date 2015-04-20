# install-lattice script

### Description
Script that allows to install [lattice](http://lattice.cf/), a small PaaS, with just one move. 

Tested on Mac OS X 10.10 with terraform 0.4.2.

### How to use
I use [direnv](http://direnv.net/) utility to load automatically environment variables from `.envrc` file. You can install it with `brew install direnv` command or use another way to manage env variables.

To prepare for deployment fill in all varaibles in `.envrc` file. Just copy `.envrc.example` to `.envrc` and fill in necessary data:
```
cp .envrc.example .envrc
```

Pay attention to the following:
- Key pair specified by `AWS_KEY_NAME` variable must present in AWS region specified by `AWS_REGION` variable, you can manage key pairs [on this page](https://console.aws.amazon.com/ec2/v2/home?region=us-west-1#KeyPairs:sort=keyName);
- `AWS_KEY_PATH` should be a path to a private key, assotiated with `AWS_KEY_NAME` key pair
- check if you don't reach a limit of VPCs on [this page](https://console.aws.amazon.com/vpc/home?region=us-west-1#vpcs:), by default this limit is 5.

After you prepared everything you can run installer:
```bash
. .envrc    # load environment variables if you don't have direnv
./install-lattice
```

### Afterwords

Feel free to contribute or ask questions using issues
