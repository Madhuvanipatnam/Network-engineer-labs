# End-to-End Connectivity Test

## Test 1

PC1

```
ip dhcp
```

Result

✅ DHCP Success

---

## Test 2

```
ping 10.10.10.1
```

Result

✅ HSRP Gateway Reachable

---

## Test 3

```
ping 192.168.13.1
```

Result

✅ R1 Reachable

---

## Test 4

```
ping 203.0.113.2
```

Result

✅ ISP1 Reachable

---

## Test 5

```
ping 8.8.8.8
```

Result

✅ Internet Reachable

---

## Test 6

On R1

```
show ip nat translations
```

Result

Dynamic NAT entries created.

---

## Conclusion

The enterprise network is fully operational.

Verified Features

- DHCP
- VLANs
- HSRP
- EtherChannel
- OSPF
- eBGP
- NAT/PAT
- Internet Connectivity
