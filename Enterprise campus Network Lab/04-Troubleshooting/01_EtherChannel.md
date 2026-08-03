# EtherChannel Troubleshooting

## Issue

The Port-Channel was not forming successfully.

```
show etherchannel summary
```

Output:

```
Po1(RD)
```

Ports were shown as:

```
Et0/1(s)
Et0/2(s)
```

---

## Cause

Incorrect physical interfaces were added to the EtherChannel.

Initially the EtherChannel was configured using the wrong interface numbers.

---

## Resolution

Configured the correct interfaces:

```
interface range e0/1 - 2
 no switchport
 channel-group 1 mode active
```

Verified using:

```
show etherchannel summary
```

Expected Output

```
Po1(RU)

Et0/1(P)

Et0/2(P)
```

---

## Result

✅ Layer 3 EtherChannel successfully established.
