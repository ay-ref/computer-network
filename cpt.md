# cisco packet tracer

## router

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
