
from django.db import models

class ShippingRate(models.Model):
    """Model to store shipping rates for different zones"""
    zone_name = models.CharField(max_length=100)
    base_price = models.DecimalField(max_digits=10, decimal_places=2)
    price_per_kg = models.DecimalField(max_digits=10, decimal_places=2)
    price_per_km = models.DecimalField(max_digits=10, decimal_places=2)
    
    def __str__(self):
        return f"{self.zone_name} - ${self.base_price}"

class Carrier(models.Model):
    """Model for different shipping carriers"""
    name = models.CharField(max_length=100)
    base_rate = models.DecimalField(max_digits=10, decimal_places=2)
    service_type = models.CharField(max_length=50)
    delivery_days = models.IntegerField()
    
    def __str__(self):
        return self.name
