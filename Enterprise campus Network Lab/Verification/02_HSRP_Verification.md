# HSRP Verification

## Objective

Verify gateway redundancy for all VLANs.

---

## Command

```
show standby brief
```

---

## Expected Result

DSW1

```
Vlan10 Active
Vlan20 Active
Vlan30 Active
Vlan40 Active
```

DSW2

```
Vlan10 Standby
Vlan20 Standby
Vlan30 Standby
Vlan40 Standby
```

---

## Virtual Gateway

```
10.10.10.1
10.20.20.1
10.30.30.1
10.40.40.1
```

---

## Result

✅ Gateway redundancy verified.
