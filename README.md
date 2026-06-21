# Citrus Board
A RP2350 based devboard with LiPO and HSTX support!

I made this since I wanted an alternative to the mainstream RP2350/2040 boards (like the xiaos), but with support for the more niche features of the chip that aren't exposed on almost all of them, like HSTX ([page 1203](https://pip-assets.raspberrypi.com/categories/1214-rp2350/documents/RP-008373-DS-2-rp2350-datasheet.pdf#page=1203)), which allows you to easily add an external display (or even camera) without sacrificing a lot the small computing power of the small chip, or even LiPo support (although most boards have it (except for the Raspberry Pi Pico), many don't have a dedicated charging IC to both support the chip's usage and to charge the battery at the same time). Additionally, it has 26 pins, indicator LEDs for charging and power, the HSTX 22pin ribbon cable terminal (which can be used with libraries like [this](https://github.com/adafruit/Adafruit-DVI-HSTX) from Adafruit) and a debug connector that is exactly compatible with the oficial [Raspberry Pi Debug Probe
](https://www.raspberrypi.com/documentation/microcontrollers/debug-probe.html).

![](/images/hero-no-bg.png)

## Repo Structure
* [/pcb](/pcb) - My KiCad design files
* [/production](/production) - Everything you need to manufacture your own! Includes gerbers, a bom and positioning files
* [/images](/images) - Images of my PCB and 3D view! (Zine is in [/zine](/zine))
* [/plots](/plots) - Schematic plot (SVG and PNG) and separate layer outlines in DXF format
* [/cad](/cad) - A step file of my PCB for reference when building projects around it
* [/bom](/bom) - My BOMs (like the below tables) stored in a CSV format

## Schematic
![](/plots/citrus-board.png)
## PCB
![](/images/pcb.png)
## 3D View
![](/images/hero-no-bg.png)
![](/images/top-no-bg.png)
![](/images/back-no-bg.png)


## BOM
### Component BOM
| Designator                                           | Footprint                                            | Quantity | Value                                | LCSC Part # | Total Cost (USD) |
|------------------------------------------------------|------------------------------------------------------|----------|--------------------------------------|-------------|------------------|
| C1, C2                                               | 0402                                                 | 2        | 15p                                  | C1548       | 0.0088           |
| C10, C12, C14, C5, C6, C9                            | 0402                                                 | 6        | 4.7u                                 | C23733      | 0.2328           |
| C11, C13, C17, C18, C19, C20, C21, C22, C23, C27, C8 | 0402                                                 | 11       | 100n                                 | C307331     | 0.0682           |
| C15, C16, C4, C7                                     | 0805                                                 | 4        | 10u                                  | C1713       | 1.6848           |
| C3                                                   | 603                                                  | 1        | 1u                                   | C1592       | 0.0312           |
| D1                                                   | 0805                                                 | 1        | ORANGE                               | C2296       | 0.0304           |
| D2                                                   | 0603                                                 | 1        | RED                                  | C2286       | 0.0144           |
| J1                                                   | USB-C-SMD_TYPE-C-6PIN-2MD-073                        | 1        | SHOU_HAN_USB_C_Receptacle_USB2.0_16P |             | 0.2205           |
| J2                                                   | JST_PH_B2B-PH-K_1x02_P2.00mm_Vertical                | 1        | Conn_01x02                           | C131337     | 0.1041           |
| J3                                                   | JST_SH_SM03B-SRSS-TB_1x03-1MP_P1.00mm_Horizontal     | 1        | Conn_01x03_MountingPin               | C160389     | 1.3305           |
| J4                                                   | CONN-SMD_AFC01-S22FCA-HF                             | 1        | 0.5mm FPC                            | C49260526   | 0.2614           |
| L1                                                   | IND-SMD_L3.9-W3.9                                    | 1        | 2.2uH                                | C20416998   | 2.2494           |
| L2                                                   | IND-SMD_L2.0-W1.6_AOTA-B201610S3R3-101-T             | 1        | 3.3uH                                | C42411119   | 1.4085           |
| R1                                                   | 0402                                                 | 1        | 1.18k                                | C270651     | 0.01             |
| R10                                                  | 0402                                                 | 1        | 1k                                   | C270651     | 0.0022           |
| R11                                                  | 0402                                                 | 1        | 33R                                  | C25105      | 0.002            |
| R12, R15, R17, R6                                    | 0402                                                 | 4        | 10k                                  | C25744      | 0.0232           |
| R13, R14                                             | 0402                                                 | 2        | 27R                                  | C25100      | 0.02             |
| R16                                                  | 0805                                                 | 1        | 0                                    | C17477      | 0.006            |
| R2                                                   | 0402                                                 | 1        | 1.13k                                | C67014      | 0.018            |
| R3                                                   | 0402                                                 | 1        | 50                                   | C227387     | 0.016            |
| R4, R5                                               | 0402                                                 | 2        | 5k1                                  | C25905      | 0.0036           |
| R7                                                   | 0402                                                 | 1        | 1.5k                                 | C25867      | 0.0022           |
| R8                                                   | 0402                                                 | 1        | 100                                  | C25076      | 0.0024           |
| R9                                                   | 0402                                                 | 1        | 100k                                 | C25741      | 0.0078           |
| SW1, SW2                                             | SW-SMD_L3.9-W3.0-P4.45                               | 2        | SW_Push                              | C720477     | 0.2208           |
| U1                                                   | VQFN-16-1EP_3x3mm_P0.5mm_EP1.6x1.6mm                 | 1        | BQ24074RGT                           | C54313      | 4.7728           |
| U2                                                   | Texas_DRC0010J_ThermalVias                           | 1        | TPS63000-Q1                          | C28060      | 3.5514           |
| U3                                                   | RP2350-QFN-60-1EP_7x7_P0.4mm_EP3.4x3.4mm_ThermalVias | 1        | RP2354A                              | C41378174   | 2.678            |
| U4                                                   | SOIC-8_5.3x5.3mm_P1.27mm                             | 1        | W25Q128JVS                           | C97521      | 4.8534           |
| Y1                                                   | Crystal_SMD_3225-4Pin_3.2x2.5mm                      | 1        | Crystal_GND24                        | C20625731   | 1.4655           |
|||||||
| Total                                                |                                                      |          |                                      |             | 25.3003          |

![](/images/jlc-breakdown.png)

### Overall BOM
| Item              | Cost (USD) | Notes |
|-------------------|------------|-------|
| PCB               | $7         |       |
| Castellated Edges | $37.70     | Not strictly required, see note 2 [here](https://jlcpcb.com/help/article/what-is-castellated-holes). If you want to save on costs, it is not necessary, but will result in a slightly lower quality finish. |
| PCB Shipping      | $1.50      |       |
| PCBA              | $80.72     |       |
||||
| Total | $89.22 ||

## Zine!!
![](/zine/zine.png)
