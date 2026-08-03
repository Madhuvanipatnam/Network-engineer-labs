# EtherChannel Verification

## Objective

Verify successful LACP EtherChannel formation between DSW1 and DSW2.

---

## Command

```
show etherchannel summary
```

---

## Expected Output

```
Po1(RU)

Et0/1(P)

Et0/2(P)
```

RU = Routed Port-Channel Up

P = Port bundled

---

## Verify Interface

```
show ip interface brief
```

Port-channel1

```
192.168.34.1
```

and

```
192.168.34.2
```

---

## Result

✅ LACP EtherChannel working successfully.
