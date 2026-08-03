# Default Route Troubleshooting

## Issue

PC1 could reach R1 but not the Internet.

```
ping 8.8.8.8
```

failed.

---

## Cause

The distribution switches did not have a default route.

```
show ip route
```

Output

```
Gateway of last resort is not set
```

---

## Resolution

Configured a static default route on R1.

```
ip route 0.0.0.0 0.0.0.0 203.0.113.2
```

Advertised it into OSPF.

```
router ospf 1

default-information originate
```

---

## Verification

On DSW1

```
show ip route
```

Expected

```
Gateway of last resort
```

---

## Result

✅ Internet reachability restored.
