# Feature Highlights 
* CPU: ALLWINNER H616, Quad-core Cortex-A53 @1.5GHz
* GPU: Mali G31 MP2, Support OpenGL3.2
* RAM: 512MB/1GB DDR3L SDRAM
* Display: Compatible with HDMI2.0A Interface, Support 4K Displays
* Compatible with USB2.0 Interface
* Support 100M Ethernet + 100M WiFi
* Having the same BTB header as the Raspberry Pi CM4.

# Specifications 
* Product Size: 40mm x 55mm
* Mounting Size: 33mm x 48mm
* Input Voltage: 5V±5%/2A
* Output Voltage: 3.3V±2%/100mA
* Output Voltage: 1.8V±2%/100mA
* WiFi: 2.4G/802.11 b/g/n

# Dimensions
<img src=img/CB1_Size.png/><br/>

# 2 * 100 pins
A Pin | Signal | Description | A Pin | Signal | Description | B Pin | Signal | Description | B Pin | Signal | Description 
-- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | --
1 | GND | | 2 | GND | | 101 | NC | | 102 | NC |
3 | NC  | | 4 | EPHY-TXP  | Ethernet TX Positive | 103 | USB1-DM | Host USB1 | 104 | LineOut L |
5 | NC  | | 6 | EPHY-TXN  | Ethernet TX Negative | 105 | USB1-DP | Host USB1 | 106 | LineOut R |
7 | GND | | 8 | GND | | 107 | GND | | 108 | GND |
9 | NC  | | 10 | EPHY-RXP  | Ethernet RX Positive | 109 | NC | | 110 | NC |
11 | NC  | | 12 | EPHY-RXN  | Ethernet RX Negative | 111 | TV_OUT | CVBS OUT | 112 | NC |
13 | GND | | 14 | GND | | 113 | GND | | 114 | GND |
15 | LINK_LED | Ethernet LED | 16 | NC | | 115 | NC | | 116 | NC |
17 | SPD_LED | Ethernet LED | 18 | NC | | 117 | NC | | 118 | NC |
19 | NC | | 20 | NC | | 119 | GND | | 120 | GND |
21 | PH5 | System LED(ACT) | 22 | GND | | 121 | NC | | 122 | NC |
23 | GND | | 24 | PC15 | | 123 | NC | | 124 | NC |
25 | PC8 | | 26 | PC6 | | 125 | GND | | 126 | GND |
27 | PH10 | | 28 | NC | | 127 | NC | | 128 | USB3-DM | Host USB3
29 | NC | | 30 | PG6 | | 129 | NC | | 130 | USB3-DP | Host USB3
31 | PG9 | | 32 | GND | | 131 | GND | | 132 | GND |
33 | GND | | 34 | NC | | 133 | NC | | 134 | USB2-DM | Host USB2
35 | PG7 | | 36 | NC | | 135 | NC | | 136 | USB2-DP | Host USB3
37 | PG8 | | 38 | PH6 | | 137 | GND | | 138 | GND |
39 | NC | | 40 | PH8 | | 139 | NC | | 140 | USB0-DM | OTG USB
41 | NC | | 42 | GND | | 141 | NC | | 142 | USB0-DP | OTG USB
43 | GND | | 44 | PH7 | | 143 | NC | | 144 | GND |
45 | PC9 | | 46 | PC10 | | 145 | NC | | 146 | NC |
47 | PC11 | | 48 | PC12 | | 147 | NC | | 148 | NC |
49 | PC13 | | 50 | PC14 | | 149 | NC | | 150 | GND |
51 | SoC_RX | DEBUG UART | 52 | GND | | 151 | HCEC | HDMI CEC | 152 | NC |
53 | GND | | 54 | PC7 | | 153 | HHPD | HDMI HotPlug | 154 | NC |
55 | SoC_TX | DEBUG UART | 56 | NC | | 155 | GND | | 156 | GND |
57 | SDC0-CLK | MicroSD Card | 58 | NC | | 157 | NC | | 158 | NC |
59 | GND | | 60 | GND | | 159 | NC | | 160 | NC |
61 | SDC0-D3 | MicroSD Card | 62 | SDC0-CMD | MicroSD Card | 161 | GND | | 162 | GND |
63 | SDC0-D0 | MicroSD Card | 64 | PG11 | | 163 | NC | | 164 | NC |
65 | GND | | 66 | GND | | 165 | NC | | 166 | NC |
67 | SDC0-D1 | MicroSD Card | 68 | PG12 | | 167 | GND | | 168 | GND |
69 | SDC0-D2 | MicroSD Card | 70 | PG13 | | 169 | NC | | 170 | HTX2P | HDMI TX2 Positive
71 | GND | | 72 | PG14 | | 171 | NC | | 172 | HTX2N | HDMI TX2 Negative
73 | PG16 | | 74 | GND | | 173 | GND | | 174 | GND |
75 | NC | | 76 | PI16 | MicroSD Card detect | 175 | NC | | 176 | HTX1P | HDMI TX1 Positive
77 | 5V | | 78 | NC | | 177 | NC | | 178 | HTX1N | HDMI TX1 Negative
79 | 5V | In 2A | 80 | NC | | 179 | GND | | 180 | GND |
81 | 5V | In 2A | 82 | NC | | 181 | NC | | 182 | HTX0P | HDMI TX0 Positive
83 | 5V | In 2A | 84 | 3.3V | Out 200mA | 183 | NC | | 184 | HTX0N | HDMI TX0 Negative
85 | 5V | In 2A | 86 | 3.3V | Out 200mA | 185 | GND | | 186 | GND |
87 | 5V | In 2A | 88 | 1.8V | Out 100mA | 187 | NC | | 188 | HTXCP | HDMI CLK Positive
89 | NC | | 90 | 1.8V | Out 100mA | 189 | NC | | 190 | HTXCN | HDMI CLK Negative
91 | NC | | 92 | PWRON | | 191 | GND | | 192 | GND |
93 | FEL | | 94 | NC | | 193 | NC | | 194 | NC |
95 | NC | | 96 | NC | | 195 | NC | | 196 | NC |
97 | NC | | 98 | GND | | 197 | GND | | 198 | GND |
99 | Recovery | | 100 | Reset | | 199 | HSDA | HDMI I2C | 200 | HSCL | HDMI I2C

