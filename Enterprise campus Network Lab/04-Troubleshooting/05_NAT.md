# NAT Troubleshooting

## Issue

PC1 could reach the ISP but not the Internet.

```
show ip nat translations
```

showed

```
No translations
```

---

## Cause

NAT was not configured correctly on R1.

The inside and outside interfaces were not defined.

---

## Resolution

Configured NAT.

```
access-list 1 permit 10.10.10.0 0.0.0.255
access-list 1 permit 10.20.20.0 0.0.0.255
access-list 1 permit 10.30.30.0 0.0.0.255
access-list 1 permit 10.40.40.0 0.0.0.255

ip nat inside source list 1 interface GigabitEthernet1/0 overload
```

Configured interfaces.

```
interface e5/0

ip nat inside

interface e5/1

ip nat inside

interface g1/0

ip nat outside
```

---

## Verification

```
show ip nat translations
```

Expected

Dynamic NAT entries.

---

## Result

✅ PAT working successfully.
