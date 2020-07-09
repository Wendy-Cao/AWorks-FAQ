GPIO 引脚电平翻转无效
======================================

关键字
-------

- GPIO引脚 翻转

问题描述
---------

配置GPIO引脚为 输出模式初始化为低和下拉电阻 时，无法翻转电平。


分析诊断
---------

配置引脚时出错。配置时应配置的 AW_GPIO_OUTPUT_INIT_LOW 错填为 AW_GPIO_OUTPUT_INIT_LOW_VAL 导致配置错误。


解决办法
---------
GPIO引脚功能应为：

* AW_GPIO_INPUT

* AW_GPIO_OUTPUT

* AW_GPIO_OUTPUT_INIT_HIGH

* AW_GPIO_OUTPUT_INIT_LOW
   
   
引脚模式应为：

* AW_GPIO_PULL_UP

* AW_GPIO_PULL_DOWN

* AW_GPIO_FLOAT

* AW_GPIO_OPEN_DRAIN

* AW_GPIO_PUSH_PULL

注意：正确的配置宏后没有 _VAL 后缀