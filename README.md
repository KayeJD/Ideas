# Ideas

## Idea 1 

App Idea: "FlexSkill" - On-Demand Micro-Gig Marketplace
Description:
FlexSkill is a platform that connects people offering small, high-demand tasks or services with individuals or businesses that need them. It's like a hyper-localized combination of TaskRabbit and Fiverr, designed for the gig economy but tailored to short-term, skill-based work.

Key Features:

Quick Matching System:

AI-driven matching algorithm that pairs users with the best local gig opportunities based on location, skills, and availability.
Micro-Gigs:

Users can list or browse small gigs such as assembling furniture, running errands, providing tutoring, dog walking, coding quick scripts, or even offering "rent-a-brain" consulting sessions.
Instant Payments:

Built-in payment system ensures quick transactions, leveraging blockchain for transparency and minimal fees.
Skill Verification & Ratings:

Users can verify skills via tests or certifications to instill trust.
Both service providers and clients can leave reviews.
Subscription Plans for Frequent Users:

Affordable subscription tiers for businesses or individuals with frequent task needs, offering discounts or premium placement in searches.
Community & Upskilling:

Access to free or low-cost skill development resources and community forums for networking.
Why It’s Profitable:

Expanding Gig Economy:

The gig economy is booming, especially in a world where people value flexibility over traditional employment.
Low Barrier to Entry:

Easy for people to list their skills or tasks, making it attractive for users across socioeconomic groups.
Local Optimization:

Hyper-local focus ensures reduced competition and faster service delivery.
Monetization:

Transaction fees for gigs completed.
Subscription options for businesses or premium users.
Ads for local businesses seeking skilled workers.
Marketable During Economic Downturns:

Encourages income generation for people who need quick cash or additional income streams.
Differentiators:

## Idea 2

App that can use links to track availability of items online thru web scraping or api

Unlike large platforms, this app focuses on micro-gigs that can be done in an hour or two, targeting tasks too small for big freelancing platforms.
Hyper-local targeting ensures relevance for both parties.
Promotes upskilling to increase user retention and engagement.

** Idea 3

Backend software with full software testing APIs. Find codecanal project. 


** CAPSTONE WORKFLOW

High-Level Workflow
1. Prepare the Hardware
Goal: Set up the ZCU106 board to run a Linux operating system and connect it to peripherals like an external screen.
Actions:
Ensure the ZCU106 board is powered and connected to your PC via UART/serial, Ethernet, and HDMI/DisplayPort for the external display.
Download the Board Support Package (BSP) for the ZCU106 from the AMD/Xilinx website.
2. Use PetaLinux to Build the Embedded Linux System
Goal: Create a bootable Linux image tailored to the ZCU106 board that supports your Qt QML application.
Create a PetaLinux Pro



Use Vitis to load the bitstream and boot files onto the board.
Open Vitis, create a platform project, and program the FPGA with the bitstream and FSBL.
4. Cross-Compile the Qt QML Application
Goal: Compile your Qt application for the ARM Cortex-A53 processor on the Zynq UltraScale+.
Install the Cross-Compilation SDK:


Install Qt Creator and configure a custom kit using the PetaLinux cross-compiler (arm-linux-gnueabihf-g++) and sysroot.
Build the Application:

Open  Qt QML project in Qt Creator and compile it using the cross-compilation kit.
The output will be a binary executable that can run on the ZCU106.
5. Deploy and Run the Application on the Board

Goal: Transfer the Linux image and your Qt QML application to the ZCU106 and run it.
Transfer Files to the Board:

Copy the boot files (BOOT.BIN, image.ub, rootfs.tar.gz) and your Qt QML application binary to the board using scp or an SD card.
Boot the ZCU106:

Insert the SD card (if used) or boot the board via QSPI or eMMC.
Once the board boots, access it via UART or SSH.
Run the Application:

Mount the root filesystem (if necessary) and navigate to  application binary:

chmod +x <your_qt_application>
./<your_qt_application>
The application should now display on the external screen connected to the ZCU106.
Roles of PetaLinux and Vitis in the Project
PetaLinux
Builds the embedded Linux OS tailored to the ZCU106 hardware.
Packages essential components (bootloader, kernel, root filesystem).
Provides the cross-compilation SDK to build your Qt application for the ARM processor.
Handles hardware-specific configurations, like enabling HDMI or DisplayPort for display output.
Vitis
Programs the FPGA hardware (loads the bitstream) and prepares the board for Linux to run.
Packages boot images in some cases (e.g., FSBL + bitstream + U-Boot).
Provides debugging and profiling tools for hardware-software interactions.
Summary of Workflow
Set up PetaLinux:

Build the Linux system with Qt and display support.
Generate the cross-compilation SDK for your Qt application.
Use Vitis:

Program the FPGA with the bitstream.
Prepare and debug hardware/software interactions.
Cross-Compile and Deploy:

Cross-compile your Qt QML application using the PetaLinux SDK.
Deploy the Linux image and application to the board.
Run the Application:

Boot the board, run the application, and view it on the external screen.



CAPSTONE NOTES:

Tried to run using BSP

successful build

boot with sd card
