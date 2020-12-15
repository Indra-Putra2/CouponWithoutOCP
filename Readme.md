## Coupun without OCP
merupakan aplikasi prehitungan coupon dengan menerapkan ```Open
Close Principle```

## How does it works
```csharp
static void Main(string[] args)
        {
            Coupon coupon1 = new Coupon();
            coupon1.discNominal = 2000;
            Console.WriteLine(coupon1.priceNett(10000));

            Coupon coupon2 = new Coupon();
            coupon2.discPercentage = 15;
            Console.WriteLine(coupon2.priceNett(10000));

            Coupon coupon3 = new Coupon();
            coupon3.discPercentage = 90;
            coupon3.discNominal = 3000;
            Console.WriteLine(coupon3.priceNett(10000));
        }
```
digunakan untuk menjalankan aplikasi perhitungan coupon

```csharp
public double priceNett(double originPrice)
        {
            double net = 0;
            if (discNominal == 0 && discPercentage > 0)
            {
                net = (100 - discPercentage) * originPrice / 100;
            }
            else if (discNominal > 0 && discPercentage == 0)
            {
                net = originPrice - discNominal;
            }
            else if (discNominal > 0 && discPercentage > 0)
            {
                net = originPrice - discNominal;
            }
            return net;
        }
```
digunakan untuk logika utama perhitungan coupon

```csharp
if (discNominal == 0 && discPercentage > 0)
            {
                net = (100 - discPercentage) * originPrice / 100;
            }
```
logika yg di gunakan ketika ```discNominal``` sama dengan 0 dan
```discPercentage``` kurang dari 0

```csharp
else if (discNominal > 0 && discPercentage == 0)
            {
                net = originPrice - discNominal;
            }
```
logika yg di gunakan ketika ```discNominal``` lebih besar dari 0 dan
```discPercentage``` sama dengan 0

```csharp
else if (discNominal > 0 && discPercentage > 0)
            {
                net = originPrice - discNominal;
            }
```
logika yg di gunakan ketika ```discNominal``` lebih besar dari 0 dan
```discPercentage``` lebih besar dari 0