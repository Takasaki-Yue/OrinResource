# <div align=cenyer>安裝BNO055 Gyro Sensor所需工具與程式庫</div>

- 前置條件:

 - 完成 **__Pyenv 安裝配置與使用__** 章節

- 安裝工具 **I2C Tools**
 `bash
 sudo apt install i2c-tools -y
 `

- 檢查 **BNO055 Gyro Sensor** 是否已經連接
 `bash
 sudo i2cdetect -y -r 7
 `
 * 檢查 **'20x8'** 的位置是否有 **'28'** 或是 **'29'** 這兩個數字，如果有就代表 BNO055 已經連接成功。

- 安裝 **BNO055 Gyro Sensor** 的主要與依賴程式庫
`bash
pip install --upgrade --user pip
pip install --upgrade --user adafruit-circuitpython-bno055 Jetson.GPIO smbus2
`