# cisco packet tracer

## general

- help: `?` is for help
  - ex: `show ip ?`

## router

### ip addressing

- static addressing (against dhcp)

```shell
ip address ipaddress subnetmask
```

### routing table

- see the `routing table`

```shell
show ip route
```

- set `routing table`

```shell
ip route destinationnetworkip subnetmaskip nextrouterportip
```

### nat

- see the `nat table`

```shell
show ip nat translations
```

- see the `nat history`

```shell
show ip nat statistics
```

- set `nat table`

  ```shell
  enable
  config t
  ```
  
  - static
    - in intermediary router

        ```shell
        ip nat inside source static <privateip> <newuniquepublicip>
        ```

    - in intermediary router private port

        ```shell
        interface interfacename
        ip nat inside
        exit
        ```

    - in intermediary router public port

        ```shell
        interface interfacename
        ip nat outside
        exit
        ```

  - dynamic (with port or without port)

    ```shell
    ip nat pool <poolname> <ipstartrange> <ipendrange> prefix <subnetprefix> 
    access-list <listnumber> permit <networkip> <wildcard>
    ip nat inside source list <listnumber> pool <poolname> [overload]
    ```

    - see access-lists

    ```shell
    show access-list
    ```

    > pool is where new ips can be made. \
    > access-list is what private ip's can has access in this subnet. \
    > pool specified with name but list specified with number!

### vlan

```shell
interface FastEthernet0/0.1
```

```shell
encapsulation dot1q <vlannumber>
```

```shell
ip address <subinfip> <netmask>
```
