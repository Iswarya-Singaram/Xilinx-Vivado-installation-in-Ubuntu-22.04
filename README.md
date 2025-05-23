# Xilinx Vivado 2024.2 Installation Guide on Ubuntu 22.04

This README provides step-by-step instructions to install **Xilinx Vivado 2024.2** on Ubuntu 22.04, focusing on a minimal installation for Verilog/VHDL design, simulation, synthesis, and bitstream generation. This setup excludes embedded software tools like Vitis.

---

## Prerequisites

- Ubuntu 22.04 LTS (64-bit)
- At least 85 GB free disk space (can be reduced by unchecking extras)
- Internet connection to download dependencies and installer

---

## Step 1: Install Required Dependencies

~~~
sudo dpkg --add-architecture i386
sudo dpkg-reconfigure dash
sudo apt update
sudo apt install -y libtinfo5 libncurses5 libncursesw5 libtinfo6 libncurses6
libc6-dev-i386 g++ unzip make graphviz xvfb git net-tools
~~~

---

## Step 2: Download Vivado Installer

1. Visit [Xilinx Downloads](https://www.xilinx.com/support/download.html).
2. Log in or create a free account.
3. Download the file:  
   `FPGAs_AdaptiveSoCs_Unified_2024.2_1113_1001_Lin64.bin`  
   Save it to your `~/Downloads` folder.
   <p align=center>
<img src="https://github.com/user-attachments/assets/1aca2102-a39f-42ce-8ac8-17b54c8042ff" height="300">
</p>

---

## Step 3: Run the Installer
~~~
cd ~/Downloads
chmod +x FPGAs_AdaptiveSoCs_Unified_2024.2_1113_1001_Lin64.bin
sudo ./FPGAs_AdaptiveSoCs_Unified_2024.2_1113_1001_Lin64.bin
~~~

- The GUI installer will launch.

---

## Step 4: Select Installation Options

- Accept all license agreements.

- Under **Design Tools**:
  - ✔️ Select **Vivado** only.
  - ❌ Deselect all Vitis-related tools (Vitis HLS, Networking, Embedded Dev, etc.).
 
    <p align=center>
<img src="https://github.com/user-attachments/assets/6367aa88-6904-45d5-be56-cf5c0a72199a">
</p>

- Under **Editions**:
  - ✔️ Select **Vivado ML Standard** (free, no license required).
  - ❌ Do NOT select Vivado ML Enterprise unless you have a paid license.

    <p align=center>
<img src="https://github.com/user-attachments/assets/1c014697-55c8-4098-92d8-3111cab325d5">
</p>

- Under **Devices**:
  - ✔️ Select **7 Series (limited support)** (includes Spartan-7, Artix-7, Zynq-7000).
  - ❌ Deselect UltraScale, Versal, SoCs, Kria, etc.

    <p align=center>
<img src="https://github.com/user-attachments/assets/3fd373e9-c890-47f3-b44f-1623640c90a5">
</p>

- Choose the install directory (default `/tools/Xilinx` recommended).

  <p align=center>
<img src="https://github.com/user-attachments/assets/b0b3387a-9745-4a76-89c9-526c0924c66f">
</p>

- Check both license agreement boxes.

  <p align=center>
<img src="https://github.com/user-attachments/assets/3ab35a4c-17b5-4164-a9eb-fd9d377ff598">
</p>

- Click **Next** and proceed with installation.
---

## Step 5: Launch Vivado
~~~
cd /tools/Xilinx/Vivado/2024.2/bin
./vivado
~~~

---

## Step 6: Create Your First Project

1. Click **Create New Project**.
2. Enter project name and select a folder in your home directory (e.g., `~/vivado_projects`).

 <p align=center>
<img src="https://github.com/user-attachments/assets/fa023809-f796-4d81-83a2-6aeed39dc884">
</p>

3. Choose **RTL Project**.
   
   <p align=center>
<img src="https://github.com/user-attachments/assets/6f00a143-bd20-45bf-ac41-b0d1b4ce066d" >
</p>

4. Check **Do not specify sources at this time**.

   <p align=center>
<img src="https://github.com/user-attachments/assets/6f00a143-bd20-45bf-ac41-b0d1b4ce066d">
</p>

5. Select a target device (e.g., Spartan-7 `xc7k70tfbg676-1`) for simulation and schematic viewing.

   <p align=center>
<img src="https://github.com/user-attachments/assets/9a244563-6fcb-440b-bfbc-2c923fb87a43">
</p>

6. Finish project creation.

---

## Step 7: Add Verilog Source File

1. In **PROJECT MANAGER**, click **Add Sources**.
2. Select **Add or create design sources**.
3. Click **Create File** → choose **Verilog** → name it (e.g., `and_gate`).
4. Click **OK** and then **Finish**.
5. Write your Verilog code in the editor.

---

## Notes

- **Do not create projects inside the Vivado installation directory** (`/tools/Xilinx/...`). Use your home directory or another writable location.
- This guide excludes embedded software and advanced features to keep installation size minimal.
- For programming physical boards, additional cable drivers may be required.

---

## References

- [Xilinx Official Downloads](https://www.xilinx.com/support/download.html)
- Community tutorials and installation guides

---

Happy FPGA designing! 🎉
