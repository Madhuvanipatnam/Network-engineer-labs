# HSRP Troubleshooting

## Issue

HSRP remained in the **Init** state.

```
show standby brief
```

Output

```
Init
```

---

## Cause

The VLAN interfaces were administratively down.

```
show ip interface brief
```

showed

```
Vlan10 administratively down
```

---

## Resolution

Enabled all SVIs.

```
interface vlan10
 no shutdown

interface vlan20
 no shutdown

interface vlan30
 no shutdown

interface vlan40
 no shutdown
```

---

## Verification

```
show standby brief
```

Expected

```
DSW1 Active

DSW2 Standby
```

---

## Result

✅ HSRP became Active/Standby successfully.
