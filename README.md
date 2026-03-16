# 🔥 RU: Сенсор погодозависимой автоматики (ПЗА) для Home Assistant

Эта интеграция позволяет создать сенсор, который вычисляет **целевую температуру теплоносителя** на основе **номера отопительной кривой** (от 1 до 200) и **датчика наружной температуры**. Полученная температура может использоваться для управления вашим отопительным прибором (котлом).

## ⚙ Возможности
- Определение **минимального и максимального пределов температуры** в соответствии с диапазоном, поддерживаемым вашим котлом.
- Создание **нескольких независимых сенсоров**, каждый со своими настройками.
- Настройка **формы отопительной кривой** с помощью подстройки диапазона экспоненты.
- Изменение параметров сенсора **в любой момент** без перезапуска Home Assistant.
- Дополнительный сенсор, который позволит **построить вашу отопительную кривую** и [разместить её на дашборд](https://github.com/sokolovs/wda-sensor/wiki/Adding-a-curve-to-the-dashboard).
- Дополнительный сенсор, который **обновляется с заданным интервалом**, вместо немедленного обновления.

## 📌 Дополнительные настройки (опционально)
Сенсор может дополнительно учитывать следующие параметры для более точного регулирования:
- **Температура внутри помещения**
- **Скорость ветра**
- **Влажность воздуха на улице**

---

## 🔢 Как эти параметры влияют на расчёт

### 🌡 Коррекция по температуре внутри помещения
- **Множитель по умолчанию:** `2`
- **Диапазон:** `0 – 10`
- На каждый **1°C разницы** между желаемой и фактической температурой в помещении целевая температура теплоносителя корректируется на **±2°C**.

### 🌬 Коррекция по скорости ветра
- **Множитель по умолчанию:** `0.2`
- **Диапазон:** `0 – 1`
- На каждые **5 м/с скорости ветра** целевая температура теплоносителя увеличивается на **1°C**.

### 💧 Коррекция по влажности воздуха на улице
- **Множитель по умолчанию:** `0.05`
- **Диапазон:** `0 – 0.4`
- На каждые **10% влажности** свыше 50% целевая температура теплоносителя увеличивается на **0.5°C**.

---

## 📌 Пример использования
Этот сенсор можно использовать в автоматизациях Home Assistant, чтобы динамически регулировать температуру котла, обеспечивая более эффективную и комфортную работу системы отопления.

🚀 **С этим сенсором ваша система отопления будет автоматически адаптироваться к изменяющимся погодным условиям!**

---

# 🔥 EN: Weather Driven Heating Control for Home Assistant

This integration allows you to create a sensor that calculates the required **heating system temperature** based on the **heating curve number** (from 1 to 200) and an **outdoor temperature sensor**. The calculated temperature can be used to control your heating boiler.

## ⚙ Features
- Define **minimum and maximum temperature limits** to match your boiler's supported range.
- Create **multiple independent sensors**, each with its own settings.
- Customize the **heating curve shape** by adjusting the exponent range for more precise control.
- Adjust sensor parameters **at any time** without restarting Home Assistant.
- An additional sensor that will allow **building your heating curve** and [placing it on the dashboard](https://github.com/sokolovs/wda-sensor/wiki/Adding-a-curve-to-the-dashboard).
- An additional sensor that **updates at a set interval** instead of updating immediately.

## 📌 Additional Factors (Optional)
The sensor can also consider the following parameters to refine its calculations:
- **Indoor temperature**
- **Wind speed**
- **Outdoor humidity**

---

## 🔢 **How These Parameters Affect the Calculation**

### 🌡 Indoor Temperature Correction
- **Default correction factor:** `2`
- **Adjustable range:** `0 to 10`
- For every **1°C difference** between the desired and actual indoor temperature, the heating system temperature is adjusted by **±2°C**.

### 🌬 Wind Speed Correction
- **Default correction factor:** `0.2`
- **Adjustable range:** `0 to 1`
- For every **5 m/s wind speed**, the heating system temperature is increased by **1°C**.

### 💧 Outdoor Humidity Correction
- **Default correction factor:** `0.05`
- **Adjustable range:** `0 to 0.4`
- For every **10% humidity above 50%**, the heating system temperature is increased by **0.5°C**.

---

## 📌 Example Usage
This sensor can be integrated into **Home Assistant automations** to dynamically adjust the boiler's temperature, ensuring a more **efficient** and **comfortable** heating experience.

🚀 **With this sensor, your heating system will automatically adapt to changing weather conditions!**
