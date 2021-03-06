# メタデータ

オブジェクトにKey/Value型のデータを保存することができます。システム間連携のために利用するデータを入れることが想定されます。

## Key

最大20個まで指定することができます。1文字以上40文字以内までです。

## Value

`string`型で1文字以上500文字以内を指定することができます。

## メタデータの操作

### 保存

例えば、システムで利用する`orderId`を支払いオブジェクトに保存したい場合以下のようにJSONをRequest Bodyに指定します。

```
{
  "amount": 100,
  "currency": "jpy",
  "method": "creditcard",
  "metadata": {
    "orderId": "1234"
  }
}
```

### 更新

メタデータの更新は差分更新になっています、変更があったKeyのみを更新します。Keyを削除したい場合は、Valueに`null`を指定すると削除されます。
