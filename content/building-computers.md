---
title: Building computers
date: 2023-07-28
---
You can build your own [computer](computer.md). If you need a powerful laptop, I can't help you, I don't know the meta anymore. If you want to use a desktop, do it, since you can build your own and upgrade parts as they break, rather than having to get a whole new computer every 10 years. It's no harder than putting together a LEGO set. Watch a tutorial or three on Youtube and you'll be fine. 

There are four components that determine the performance of a computer:
- **Central Processing Unit (CPU)**: The main brain of the computer, this is the thing that does all the computationg, it processes math equations. The main component that determines how "fast" your computer is.
- **Graphics Processing Unit (GPU)**: A CPU-spinoff that processes simple math problems (linear equations) extremely well. Basically used for computer graphics (video games, video editing) and AI calculations.
- **RAM**: Random-access memory, used for storing all the programs that are currently running. Limits how much you can do at one time.
- **Storage/SSD/HDD**: The main memory storage of a computer, used for storing files, data, programs, etc.

And there are three components that support the others:
- **Motherboard**: The backbone of the computer, what most of the pieces connect to, the motherboard basically routes power to all of the components. The GPU, RAM, and Storage all connect directly to the motherboard. The CPU connects directly to the motherboard through a specialized connection, so *the CPU needs to have the same socket type as the motherboard to work*.
	- *ATX*: The biggest size of motherboard
	- *ITX*: Medium size motherboard
	- *Mini-ITX*: Smallest size motherboard, go with this unless you need all the other random connection points.
- **Power Supply (PSU)**: Plugs into a wall outlet and converts 120/240V current into current usable by each component of the PC. Must be able to supply more power than what the other components will use, so that you don't short circuit your CPU/GPU/RAM/Storage/Motherboard.
- **Case**: Technically not even necessary, the case just holds all the other components suspended in the air so that they can get more air flow.

### How to pick parts
Use an online tool like [PCPartPicker](https://pcpartpicker.com/list/) to double check compatability of all the components of your system. You should verify with the manufacturer specifications as well.

## CPU and Motherboard
The CPU is the most essential part of the build, so get a good one, and make sure to get a motherboard that matches sockets with your CPU. This is the backbone of your build.

## GPU
If your CPU includes integrated graphics you’re good to go for basic tasks. But for gaming or video editing, a discrete GPU is essential. Modern motherboards generally support PCIE slots, ensuring compatibility with most modern GPUs. However, it’s always a good idea to double-check this before purchasing a GPU.

## RAM and Storage
Once you’ve chosen a motherboard, look at its specifications to determine the type of memory it uses (e.g., DDR4), the number of memory slots, and compatible memory speeds. When I built my first PC I overlooked memory speed compatibility, ending up with RAM my system couldn’t fully utilize. I recommend using online tools like to verify compatibility. As for storage, check the motherboard’s hard drive interfaces (e.g., M.2, SATA). I chose an M.2 SSD for its faster boot-up speeds, sacrificing some storage space compared to a SATA SSD.

## Power Supply
After selecting all computing parts it’s time to choose a power supply unit (PSU). Calculate the power usage of all components combined and then pick a PSU with a bit more wattage for safety. Mine totaled 274W, so I opted for a 500W PSU. Look for an 80 PLUS certified PSU for better efficiency and reliability. Modular PSUs may be worth the extra cost for tidiness and ease of cable management. I chose an SFX (smaller than an ATX) PSU to fit in an 11-liter case.

## Case
In the end, your choice of case is about more than fitting all components — it’s about ensuring they all work together harmoniously. Check, and then recheck, the maximum dimensions for the motherboard, power supply, GPU, and CPU cooler. Good airflow and proper cable management are critical for maintaining optimal temperatures, and thereby performance.

Building a PC is a rewarding experience that combines technical know-how with a bit of creativity. Embrace the process, and don’t hesitate to reach out if you hit a snag. Happy building!