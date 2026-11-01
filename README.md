## About MeshCaching-Fox

MeshCaching-Fox is a firmware built on the MeshCore repeater, designed for [MeshCaching](https://tutoduino.fr/en/articles/organize-meshcaching/) activities.

The Fox acts as a standard MeshCore repeater, but additionally transmits a zero-hop beacon frame every 10 seconds. This beacon frame is used by [FoxHunter](https://github.com/tutoduino/meshcaching) to locate the Fox.

Note that only the *main.cpp* file of the *simple_repeater* example has been modified from the original MeshCore repeater code.

!! ONLY USE THIS FIRMWARE FOR MESHCACHING ACTIVITIES !!

Indeed, this firmware transmits a beacon every 10 seconds, which is useful only for direction-finding. Outside a MeshCaching activity, it wastes LoRa bandwidth and degrades the mesh for other nodes.

## Build MeshCaching-Fox firmware on Linux
Clone the repository:

    git clone https://github.com/tutoduino/MeshCaching-Fox.git

Enter the project directory:

    cd MeshCaching-Fox

install the prerequisites:

    sudo apt install platformio
    sudo apt install python3-venv python3-dev
    python3 -m venv .venv
    source .venv/bin/activate
    python -m pip install --upgrade pip
    python -m pip install --upgrade platformio

Compile the firmware for your target (for Heltec_v3 here):

    pio run -e Heltec_v3_repeater

The firmware binary is located here:

    .pio/build/Heltec_v3_repeater/firmware.bin

You can upload it to your device using Custom firmware option in MeshCore [Flasher](https://flasher.meshcore.io/):

## Configuration
Please follow guidelines available on [MeshCaching](https://tutoduino.fr/en/articles/organize-meshcaching/) page.
    
