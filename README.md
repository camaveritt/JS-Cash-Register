# Cash Register

A JavaScript function that calculates the change owed for a purchase and works out which bills and coins to give back from the cash drawer.

## How It Works

`checkCashRegister(price, cash, drawer)` takes:

| Parameter | Description |
| --- | --- |
| `price` | The price of the item |
| `cash` | The cash provided as payment |
| `drawer` | The cash in the drawer, as an array of `[name, amount]` pairs |

It returns an object with a `status` and the `change` to give back:

| Status | Meaning |
| --- | --- |
| `OPEN` | Exact change can be made, and the drawer still has money left |
| `CLOSED` | The change owed equals all the cash in the drawer |
| `INSUFFICIENT_FUNDS` | The drawer doesn't have enough money, or can't make exact change |

Change is given using the highest denominations first, from $100 bills down to pennies.

## Usage

```js
checkCashRegister(19.5, 20, [
  ["PENNY", 1.01],
  ["NICKEL", 2.05],
  ["DIME", 3.1],
  ["QUARTER", 4.25],
  ["ONE", 90],
  ["FIVE", 55],
  ["TEN", 20],
  ["TWENTY", 60],
  ["ONE HUNDRED", 100],
]);

// { status: "OPEN", change: [["QUARTER", 0.5]] }
```

To try it out, add the example above to the bottom of `cashregister.js` and run:

```bash
node cashregister.js
```

Wrap the call in `console.log()` to see the result printed.
