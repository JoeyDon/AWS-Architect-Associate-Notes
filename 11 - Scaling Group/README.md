# Scaling Group
## Key Points:

### Scaling Policies
* Manual Scaling
* Scheduled Scaling
* Dynamic Scaling
    - Simple: 'CPU 50% + 1' or Stroage. Action based on Matric
    - Stepped: Bigger +/- based on difference '50%+1, 80%+2'
    - Target Tracking. Maintain CPU = 40% ASG handles it
* Cooldown Periods

* ACG defines When and Where
* LT defines What to launch