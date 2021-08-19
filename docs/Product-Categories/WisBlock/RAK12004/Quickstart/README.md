---
rak_desc: Contains instructions and tutorials in installing and deploying your RAK12004. Instructions are written in a detailed and step-by-step manner for an easier experience in setting up your device. Aside from the hardware configuration, it also contains a software setup that includes detailed example codes that will help you get started.
tags:
  - quickstart
  - wisblock
  - RAK12004
prev: ../Overview/ 
next: ../Datasheet/ 
---

# RAK12004 Quick Start Guide
## Prerequisite

### What Do You Need?

Before going through each and every step on using RAK12004 WisBlock MQ2 module, make sure to prepare the necessary items listed below:

#### Hardware

- [RAK12004](https://store.rakwireless.com/products/mq2-gas-sensor-module-rak12004)
- Your choice of [WisBlock Base](https://store.rakwireless.com/collections/wisblock-base) 
- Your choice of [WisBlock Core](https://store.rakwireless.com/collections/wisblock-core)
- USB Cable
- Li-Ion/LiPo battery (optional)
- Solar charger (optional)

#### Software

- Download and install [Arduino IDE](https://www.arduino.cc/en/Main/Software).
- To add the RAKwireless Core boards on your Arduino project, install the RAKwireless Arduino BSP. Follow the steps in the [Github repo](https://github.com/RAKWireless/RAKwireless-Arduino-BSP-Index).

## Product Configuration

### Hardware Setup

RAK12004 module is part of the WisBlock Sensor category and extends the WisBlock system with a gas sensor alert system. The RAK12004 connects to the WisBlock Base Board through the IO slot. The **Figure 1** shows the assembly of a [WisBlock Core](https://store.rakwireless.com/collections/wisblock-core) highlighted in green and the module RAK12004 highlighted in red. Also, always secure the connection of the WisBlock module by using the compatible screws. For more information about RAK12004, refer to the [Datasheet](../Datasheet/).

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak12004_assembly.png"
  width="100%"
  caption="RAK12004 connection to WisBlock Base Board"
/>

#### Assembling and Disassembling of WisBlock Modules

##### Assembling

As shown in **Figure 2**, the location for the IO slot is properly marked by silkscreen. Follow carefully the procedure defined in [RAK5005-O module assembly/disassembly instructions](https://docs.rakwireless.com/Knowledge-Hub/Learn/RAK5005-O-Baseboard-Installation-Guide/) to attach a WisBlock module. Once attached, carefully fix the module with one or more pieces of M1.2 x 3&nbsp;mm screws depending on the module.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak12004_mounting.png"
  width="70%"
  caption="RAK12004 connection to WisBlock Base Board"
/>

##### Disassembling

The procedure in disassembling any type of WisBlock modules is the same. 

1. First, remove the screws.  

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/16.removing-screws.png"
  width="70%"
  caption="Removing screws from the WisBlock module"
/>

2. Once the screws are removed, check the silkscreen of the module to find the correct location where force can be applied.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/17.detaching-silkscreen.png"
  width="70%"
  caption="Detaching silkscreen on the WisBlock module"
/>

3. Apply force to the module at the position of the connector, as shown in **Figure 5**, to detach the module from the baseboard.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/18.detaching-module.png"
  width="70%"
  caption="Applying even forces on the proper location of a WisBlock module"
/>

::: tip 📝 NOTE
If you will connect other modules to the remaining WisBlock Base slots, check on the [WisBlock Pin Mapper](https://docs.rakwireless.com/Knowledge-Hub/Pin-Mapper/) tool for possible conflicts. RAK12004 uses I2C and IO pins it can cause possible conflict especially on some IO modules. 
:::


After all this setup, you can now connect the battery and USB cable to start programming your WisBlock Core.

### Software Configuration and Example

The RAK12004 has an electronic sensor used for sensing the concentration of gases in the air. It contains a sensing material whose resistance changes when it comes in contact with the gas. Concentrations of gas is measured using a voltage divider network present in the sensor. The output of the sensing element is connected to a 12-bit ADC (ADC121C021) which communicates through I2C to the application.

These are the quick links that go directly to the software guide for the specific WisBlock Core module you use.

- [RAK12004 in RAK4631 WisBlock Core Guide](/Product-Categories/WisBlock/RAK12004/Quickstart/#rak12004-in-rak4631-wisblock-core-guide)
- [RAK12004 in RAK11200 WisBlock Core Guide](/Product-Categories/WisBlock/RAK12004/Quickstart/#rak12004-in-rak11200-wisblock-core-guide)


#### RAK12004 in RAK4631 WisBlock Core Guide

##### Arduino Setup

Install the [RAKwireless Arduino BSP](https://github.com/RAKWireless/RAKwireless-Arduino-BSP-Index).

1. You need to select RAK4631 WisBlock Core.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak4631_board.png"
  width="100%"
  caption="Selecting RAK4631 as WisBlock Core"
/>

##### Initial Test of the RAK12004 WisBlock Module

Arduino programs are usually referred to as sketches.

2. Install the [RAKwireless MQx Library](https://github.com/RAKWireless/RAK-MQx-Library) using Arduino Library Manager.

On the Arduino IDE, select Sketch-> Include Library -> Manage Libraries, as shown in **Figure 7**. On the **Library Manager** text area, type **RAKwireless MQx**. 
<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak-mqx-lib-manager.png"
  width="100%"
  caption="Arduino Library Manager"
/>

3. To finish the installation, click on the **Install** button, as shown in **Figure 8**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak-mqx-install.png"
  width="100%"
  caption="Finish RAK-MQx library Installation"
/>

4. Once the library is installed, open the **RAK12004_MQ2_Sampling** example. On the Arduino IDE, select File-> Examples -> RAKWireless MQx Libraries -> RAK12004_MQ2_Sampling, as shown in **Figure 9**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak-mqx-samp.png"
  width="100%"
  caption="Open RAK12004 MQ2 Sampling Sketch"
/>

5. You can now select the right serial port and upload the code, as shown in **Figure 10** and  **Figure 11**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/select_port_rak4631.png"
  width="100%"
  caption="Selecting the correct Serial Port"
/>

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/upload_rak4631.png"
  width="100%"
  caption="Uploading the RAK12004 example code on RAK4631"
/>

To extend the use of the RAK-MQx library, check the link [RAK-MQx Library methods](https://github.com/RAKWireless/RAK-MQx-Library#usage)


<!-- Add log images 

6. When you successfully uploaded the example sketch, open the Serial Monitor of the Arduino IDE to check the sensor's reading logs. If you see the logs, as shown in **Figure 14**, then your RAK12004 is properly communicating to the WisBlock core.

<rk-img
  src="/assets/images/wisblock/rak1903/quickstart/optical_logs.png"
  width="80%"
  caption="RAK12004 data logs"
/>

-->

#### RAK12004 in RAK11200 WisBlock Core Guide

##### Arduino Setup

1. Install the [RAKwireless Arduino BSP](https://github.com/RAKWireless/RAKwireless-Arduino-BSP-Index).

2. You need to select RAK11200 WisBlock Core.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak11200_board.png"
  width="100%"
  caption="Selecting RAK11200 as WisBlock Core"
/>

##### Initial Test of the RAK12004 WisBlock Module

Arduino programs are usually referred to as sketches.

3. Install the [RAKwireless MQx Library](https://github.com/RAKWireless/RAK-MQx-Library) using Arduino Library Manager.

4. On the Arduino IDE, select Sketch-> Include Library -> Manage Libraries, as shown in **Figure 13**. On the **Library Manager** text area, type **RAKwireless MQx**. 

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak-mqx-lib-manager.png"
  width="100%"
  caption="Arduino Library Manager"
/>

5. To finish the installation, click on the **Install** button as shown in **Figure 14**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak-mqx-install.png"
  width="100%"
  caption="Finish RAK-MQx library Installation"
/>

6. Once the library is installed, open the **RAK12004 MQ2 Sampling** example. On the Arduino IDE, select File-> Examples -> RAKWireless MQx Libraries -> RAK12004_MQ2_Sampling, as shown in **Figure 15**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/rak-mqx-samp.png"
  width="100%"
  caption="Open RAK12004 MQ2 Sampling Sketch"
/>

7. You can now select the right serial port and upload the code, as shown in **Figure 16** and  **Figure 17**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/select_port_rak11200.png"
  width="100%"
  caption="Selecting the correct Serial Port"
/>


:::tip 📝 NOTE:
RAK11200 requires the BOOT0 pin to be configured properly before uploading. If not done properly, uploading the source code to RAK11200 will fail. Check the full details on the [RAK11200 Quick Start Guide](/Product-Categories/WisBlock/RAK11200/Quickstart/#uploading-to-wisblock).
:::

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/upload_rak11200.png"
  width="100%"
  caption="Uploading the RAK12004 example code on RAK11200"
/>


To extend the use of the RAK-MQx library, check the link [RAK-MQx Library methods](https://github.com/RAKWireless/RAK-MQx-Library#usage)

#### Build RAK12004 Example on PlatformIO IDE

1. Install the [RAKwireless PlatformIO BSP](https://docs.rakwireless.com/Knowledge-Hub/Learn/Board-Support-Package-Installation-in-PlatformIO/).

2. After installing your RAK Core board on PlatformIO, you can import the entire project to PlaformIO.

3. Import Arduino Project to PlatformIO.

4. Open PlatformIO PIO Home and select **Import Arduino Project**, as shown in **Figure 18**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/pio-home-import.png"
  width="90%"
  caption="Import RAK12004 Arduino Project"
/>

5. Select the **WisBlock Core Board** and check "**Use Libraries installed by the Arduino IDE**", option as shown in **Figure 19**. Then choose the directory of the original Arduino Project.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/import-project.png"
  width="90%"
  caption="Select Board and check Import Libraries"
/>

6. To finish the import, click on **Import** button, as shown in **Figure 20**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/finish-import.png"
  width="90%"
  caption="Select Board and check Import libraries"
/>

7. Build the imported project on the PlatformIO.

Now, you can build the project by clicking on highlighted icon as shown in **Figure 21**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/build-project.png"
  width="90%"
  caption="Build Arduino imported project"
/>

8. Upload the imported project on the PlatformIO.

9. To upload the project on the target board, click on the highlighted icon as shown in Figure **22**.

<rk-img
  src="/assets/images/wisblock/rak12004/quickstart/upload-pio-project.png"
  width="90%"
  caption="Upload Arduino imported project"
/>