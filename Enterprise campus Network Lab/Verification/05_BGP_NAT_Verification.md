# BGP and NAT Verification

## BGP

Verify neighbor status.

```
show ip bgp summary
```

Expected

R1 ↔ R3 Established

R2 ↔ R4 Established

R3 ↔ INTERNET Established

R4 ↔ INTERNET Established

---

Verify routes

```
show ip bgp
```

Expected

```
1.1.1.1

2.2.2.2

3.3.3.3

4.4.4.4

8.8.8.8
```

---

## NAT

Verify translations.

```
show ip nat translations
```

```
show ip nat statistics
```

Expected

Dynamic translations created after Internet traffic.

---

## Result

✅ BGP and NAT functioning correctly.
