# VTEX Store GraphQL

Forked from vtex.store-graphql@2.71.0. Main changes: Removing AvailableQuantity 0/10000 logic from node/utils/simulation.ts

BEFORE
node/utils/simulation.ts

```typescript
AvailableQuantity:
      orderFormItem?.availability === 'available' &&
      (logisticsInfo ? logisticsInfo.stockBalance : 1)
        ? 10000
        : 0,
```

AFTER
node/utils/simulation.ts

```typescript
AvailableQuantity:
       orderFormItem?.availability === 'available' && logisticsInfo
         ? logisticsInfo.stockBalance
         : 0,
```
