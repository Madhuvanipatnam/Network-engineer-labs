# BGP Troubleshooting

## Issue

BGP sessions were not exchanging routes.

---

## Cause

The advertised networks were missing from the BGP configuration, or the required prefixes were not present in the routing table.

---

## Resolution

Verified neighbor status.

```
show ip bgp summary
```

Advertised the required networks.

Example

```
network 1.1.1.1 mask 255.255.255.255

network 203.0.113.0 mask 255.255.255.0
```

Repeated on all BGP routers.

---

## Verification

```
show ip bgp
```

Verified the following routes:

- 1.1.1.1
- 2.2.2.2
- 3.3.3.3
- 4.4.4.4
- 8.8.8.8

---

## Result

✅ BGP route exchange successful.
