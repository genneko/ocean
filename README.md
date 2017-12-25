# ocean
A tiny wrapper for the DigitalOcean's official doctl CLI.

Supported operations are:
* create - Create a new droplet from the specified image or snapshot. Add an A record for the droplet to DNS. Optionally run the provisioning script.
* destroy - Destroy a droplet without taking a snapshot. Also remove an A record for the droplet from DNS.
* freeze - Destroy a droplet after taking a snapshot for later reuse.
* restore - Re-create a droplet from a snapshot taken by 'freeze'.
* ssh - SSH to a droplet.
* status - Check status of a droplet.
* list - List all droplets, snapshots and DNS records.

## Install
Clone this repo in a directory of your choice. Add the cloned directory to your $PATH.
```
$ cd ~/app
$ git clone git@github.com:genneko/ocean.git
or
$ git clone https://github.com/genneko/ocean.git
```

## Quick Start
1. You need one directory for each droplet. After moving into it, run 'ocean init' to generate a skelton of 'Oceanfile'. Edit the file for your need.
    ```
    $ mkdir -p ~/droplet/zfstest
    $ cd ~/droplet/zfstest
    $ ocean init
    $ vi Oceanfile
    ```

2. Create a new droplet by running 'ocean create'.
    ```
    $ ocean create
    ```

3. To see the droplet status, run 'ocean status'.
    ```
    $ ocean status
    ```

4. You can ssh into the droplet by 'ocean ssh'.
    ```
    $ ocean ssh
    ```

5. If you want to use the droplet later, freeze the droplet by 'ocean freeze'.
    ```
    $ ocean freeze
    ```

6. Re-create the droplet by 'ocean restore'.
    ```
    $ ocean restore
    ```

7. Destroy the droplet without taking a snapshot by 'ocean destroy'.
    ```
    $ ocean destroy
    ```

