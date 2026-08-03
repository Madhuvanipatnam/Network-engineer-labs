# OSPF Verification

## Objective

Verify OSPF adjacency across the enterprise network.

---

## Commands

```
show ip ospf neighbor
```

```
show ip route
```

---

## Verify

R1

```
Neighbor R2

Neighbor DSW1

Neighbor DSW2
```

R2

```
Neighbor R1

Neighbor DSW1

Neighbor DSW2
```

DSW1

```
Neighbor R1

Neighbor R2

Neighbor DSW2
```

DSW2

```
Neighbor R1

Neighbor R2

Neighbor DSW1
```

---

## Verify Default Route

```
show ip route
```

Expected

```
Gateway of last resort
```

should appear on

- DSW1

- DSW2

---

## Result

✅ OSPF fully operational.
