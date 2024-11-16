# computer-network

## router

### routing

- static routing
  - which network you want to go: **Network** (given in packet)
  - is subnetting valid: **Subnet Mask**
  - which ip of next router i should send you: **Next Hop** (wanted/task)

### private networks range

- 192.168.0.0 – 192.168.255.255 (65,536 IP addresses)
- 172.16.0.0 – 172.31.255.255 (1,048,576 IP addresses)
- 10.0.0.0 – 10.255.255.255 (16,777,216 IP addresses)

## cisco packet tracer

### routing table

- see the `routing table`

```shell
show ip route
```

- set `routing table`
  - static addressing (against dhcp)

    ```shell
    ip address ipaddress subnetmask
    ```

### nat

- see the `nat history`

```shell
show ip nat statistics
```

- set `routing table`

```shell
ip route destinationnetworkip subnetmaskip nextrouterportip
```

- set `nat table`

  ```shell
  enable
  config t

  ```
  
  - static

    ```shell
    ip nat inside source static <privateip> <newuniquepublicip>
    ...
    ```

  - dynamic

    ```shell
    ip nat pool no-overload <ipstartrange> <ipendrange> prefix <subnetprefix>
    ip nat inside source list <listnumber> pool no-overload
    access-list <listnumber> permit <networkip> <wildcard>
    ...
    ```

- see the `nat table`

```shell
show ip nat translations
```
