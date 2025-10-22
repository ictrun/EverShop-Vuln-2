# Cart Information Unauthorized Access
**Severity**: HIGH (CVSS 7.5)
**CWE**: CWE-639

#### Affected File
```
/packages/evershop/src/modules/checkout/graphql/types/Cart/Cart.resolvers.ts
Lines 12-20
```

#### Vulnerable Code

```typescript
cart: async (_, { id }) => {
try {
const cart = await getCartByUUID(id); // No authorization check
return camelCase(cart.exportData());
} catch (error) {
return null;
}
}
```

---

# Unauthorized Cart Item Deletion

**Severity**: MEDIUM (CVSS 6.5)
**CWE**: CWE-284

#### Affected File
```
/packages/evershop/src/modules/checkout/api/removeCartItem/removeItem.js
```

#### Attack Vector
```bash
# No authentication required
DELETE /api/cart/{VICTIM_CART_UUID}/items/{ITEM_UUID}
```

---

# Unauthorized Cart Item Addition

**Severity**: MEDIUM (CVSS 5.3)
**CWE**: CWE-284

#### Affected File
```
/packages/evershop/src/modules/checkout/api/addCartItem/addItemToCart.js
```


<img width="990" height="582" alt="image" src="https://github.com/user-attachments/assets/1715ffc0-5969-48b3-a850-1397d4993082" />
