# DHCP Verification

## Objective

Verify that clients receive IP addresses automatically from the DHCP server configured on DSW1.

---

## Verification Command

On PC1

```
ip dhcp
```

---

## Expected Output

```
IP Address : 10.10.10.21
Subnet Mask : 255.255.255.0
Gateway : 10.10.10.1
```

---

## Verification on DSW1

```
show ip dhcp binding
```

```
show ip dhcp pool
```

---

## Result

✅ DHCP is functioning correctly.
