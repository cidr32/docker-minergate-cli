Minergate-cli is the console miner provided by MinerGate.
=========================================================
![Docker Build Status](https://img.shields.io/docker/build/cidr32/minergate-cli.svg)
![Docker Image Size](https://img.shields.io/microbadger/image-size/cidr32/minergate-cli.svg)

How to use this image

Run in background:

$ docker run -d --name minergate-cli cidr32/minergate-cli --user email@example.com --xmr

Get minergate-cli options with:

$ docker run --rm cidr32/minergate-cli -help

Fetch logs of a container:

$ docker logs minergate-cli

# minergate-cli Usage:

minergate-cli [options] <currency-settings> <gpu-settings>

|        options:        |                   | Description                                                  |
| :--------------------: | :---------------: | :----------------------------------------------------------- |
|           -u           |      --user       | account email from minergate.com                             |
|           -v           |     --version     | show version                                                 |
|           -l           |    --list-gpu     | shows the list of available GPU devices                      |
|                        |                   |                                                              |
| **currency-settings:** |                   |                                                              |
|  --currency [threads]  |                   | instead of 'currency' use one of these values: eth, etc, btg, zec, bcn, xmr, xmo, qcn, xdn, fcn, mcn, aeon, dsh, inf8;<br><br>or merged mining use one of the follow options: --fcn+xmo, --fcn-qcn, --xdn-xmo, --fcn-dsh, --fcn-inf8, --dsh-mcn, --inf8-mcn;<br><br>[threads] is count of used CPU cores for mining |
|                        |                   |                                                              |
|   **gpu-settings:**    |                   |                                                              |
|     -g [device_no]     | --gpu [device_no] | [device_no] is the order number of device which you can find out by using this command '--list-gpu'. The miner will use the first GPU device if 'device_no' not specified. Multiple '-g' options also accepted. |
|        --no-cpu        |                   | don't use CPU for mining                                     |
|        --proxy         |                   | proxy server URL. Supports only socks protocols (for example: socks://192.168.0.1:1080) |

Examples:

  minergate-cli -u ACCOUNT-EMAIL --bcn 4

  minergate-cli --user ACCOUNT-EMAIL --eth 6 -g
  
  minergate-cli --gpu --no-cpu --user ACCOUNT-EMAIL --xmr
