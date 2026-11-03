# Iraq Cities

A list of Iraq's 19 governorates and 180 cities and districts, with names in **English**, **Arabic** and **Kurdish (Sorani)**.

Each entry has a stable `id`, so you can use the data in dropdowns, address forms, apps and websites.

## Files

| File | Contents |
|---|---|
| [`iraq_cities.json`](iraq_cities.json) | All governorates, each with its list of cities |
| [`governorates.json`](governorates.json) | Governorates only, without cities |

## Fields

| Key | Meaning |
|---|---|
| `id` | Unique id: lowercase, words joined with `-` (e.g. `tel-afar`) |
| `name_en` | Name in English |
| `name_ar` | Name in Arabic |
| `name_ckb` | Name in Kurdish (Sorani) |
| `cities` | List of cities in the governorate (`iraq_cities.json` only) |

City ids are unique across the whole file. A city id can be the same as its governorate's id (for example the `erbil` city inside the `erbil` governorate).

## Example

```json
{
  "governorates": [
    {
      "id": "erbil",
      "name_en": "Erbil",
      "name_ar": "أربيل",
      "name_ckb": "هەولێر",
      "cities": [
        {
          "id": "erbil",
          "name_en": "Erbil Center",
          "name_ar": "مركز أربيل",
          "name_ckb": "ناوەندی هەولێر"
        }
      ]
    }
  ]
}
```

### JavaScript

```js
const data = await fetch(
  "https://raw.githubusercontent.com/aryzonedev/iraq-cities/main/iraq_cities.json"
).then((r) => r.json());

const erbil = data.governorates.find((g) => g.id === "erbil");
console.log(erbil.cities.map((c) => c.name_ckb));
```

## Governorates

Erbil, Sulaymaniyah, Duhok, Halabja, Baghdad, Ninewa, Kirkuk, Diyala, Salah Al-Din, Anbar, Basra, Babil, Karbala, Najaf, Wasit, Qadisiyah, Maysan, Thi Qar, Muthanna.

## کوردی

لیستی ١٩ پارێزگا و ١٨٠ شار و قەزای عێراق، بە ناوی ئینگلیزی، عەرەبی و کوردی (سۆرانی).

- `name_en`: ناوی ئینگلیزی
- `name_ar`: ناوی عەرەبی
- `name_ckb`: ناوی کوردی
- `cities`: شارەکانی ناو پارێزگاکە

## Contributing

Found a wrong or missing name? Open an issue or a pull request.

## License

[CC BY 4.0](LICENSE). You can use, share and change this data for any purpose, including commercial use, as long as you give credit.
