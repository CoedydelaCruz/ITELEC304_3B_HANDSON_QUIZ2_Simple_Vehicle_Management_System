# Vehicle Management System

This Django project demonstrates inheritance, method overriding, and polymorphism
using Django models.

## Models

- `Vehicle` is the parent model with `brand`, `price`, and `vehicle_info()`.
- `Car` inherits from `Vehicle`, adds `doors`, and overrides `vehicle_info()`.
- `Motorcycle` inherits from `Vehicle`, adds `helmet_included`, and overrides `vehicle_info()`.

## Django Shell Testing

Run:

```powershell
python manage.py shell
```

Then enter:

```python
from vehicles.models import Car, Motorcycle

car = Car.objects.create(brand="Toyota", price=500000, doors=4)
motorcycle = Motorcycle.objects.create(
    brand="Honda",
    price=120000,
    helmet_included=True,
)

vehicles = [car, motorcycle]

for vehicle in vehicles:
    print(vehicle.vehicle_info())
```

Expected output:

```text
Toyota Car with 4 doors costs 500000
Honda Motorcycle costs 120000
```
