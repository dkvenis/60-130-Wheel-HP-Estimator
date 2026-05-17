# 60-130 mph Wheel Horsepower (WHP) Estimator

An empirical mathematical model developed to predict a vehicle's wheel horsepower (WHP) based exclusively on its total race weight and its 60–130 mph acceleration time. 

Developed by mapping real-world dyno results against verified high-precision GPS (Dragy/Dragtimes) acceleration datasets using a power-law regression line of best fit.

## 📺 Original Documentation & Methodology
The development, test data, scatter plots, and real-world validation of this formula are documented in detail on YouTube:
👉 **[Watch the Original Formula Development Video](https://youtu.be/eY_i2nBVzh0?si=7lNHUvAw_1ilpiJi)**

## 🧮 The Formula

$$\text{WHP} = t^{-1.009} \times 1.126 \times W$$

Where:
* **$t$** = 60–130 mph time in seconds
* **$W$** = Total race weight of the vehicle in pounds (including driver and fuel)

---

## 💻 Code Implementations

### Python
```python
def estimate_whp(time_seconds: float, weight_lbs: float) -> float:
    """
    Estimates wheel horsepower using the empirical 60-130mph power-law model.
    Developed by: https://youtu.be
    """
    whp = (time_seconds ** -1.009) * 1.126 * weight_lbs
    return round(whp, 1)

# Example: 3500 lbs vehicle running a 5.00 second 60-130
print(f"Estimated WHP: {estimate_whp(5.00, 3500)} hp")
```

### Microsoft Excel / Google Sheets
If your time is in cell `A2` and weight is in cell `B2`, use this formula:
```excel
=(A2^-1.009)*1.126*B2
```

---

## 📜 License & Citation
This model is free to use across the car community, tuning shops, and performance software. If you feature this formula in an online calculator, app, forum post, or media publication, please attribute the work by citing the original creator or linking back to the [original YouTube video](https://youtu.be/eY_i2nBVzh0?si=7lNHUvAw_1ilpiJi).
