# Data Dictionary (Minimal)

## farm
- `farm_id` (string): unique farm identifier
- `county` (string): county name
- `crop_type` (string): primary crop
- `farm_size_ha` (number): farm size in hectares
- `irrigation` (bool): irrigated or not

## soil
- `ph` (number): acidity level
- `nitrogen_ppm` (number): nitrogen in ppm
- `moisture_pct` (number): soil moisture percentage

## pest_observation
- `pest_name` (string): observed pest/disease
- `severity` (enum): low/medium/high

## weather_daily
- `rain_mm` (number): rainfall (mm)
- `tmin_c`, `tmax_c` (number): min/max temperature
