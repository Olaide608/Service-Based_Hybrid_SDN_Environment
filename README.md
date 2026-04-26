# A Service-Based Hybrid SDN Environment
The purpose of this lab was to use Openflows to perform basic MPLS operations (Push, Swap, and Pop)

<img width="610" height="399" alt="GITHUB1" src="https://github.com/user-attachments/assets/c40cd058-61d7-4dc0-895e-0ca2a21db609" />

# Tools Used
GNS3 – Simulation environment 

Ubuntu Linux – Used to host OpenDaylight and OpenFlow Manager

OpenDaylight Controller (Carbon version) – SDN controller - https://nexus.opendaylight.org/content/repositories/public/org/opendaylight/integration/distribution-karaf/

OpenFlow Manager – Flow management and rule injection tool - https://github.com/CiscoDevNet/OpenDayLight-OpenFlow-App

Open vSwitches – Software switches for OpenFlow-based MPLS operations - https://gns3.com/marketplace/appliances

# How It Works

This project designs and validates a service-based hybrid SDN environment using traditional routers, Open vSwitches, and an SDN controller. The aim is to show how SDN can be introduced into an existing network to provide selected programmable services, while the traditional network continues to handle normal routing and connectivity.

The traditional routers are used to represent the legacy network environment. They maintain the basic network functions, including IP routing and MPLS-related connectivity. This means the network does not fully depend on SDN for all operations, which makes the design more practical for environments where traditional infrastructure is still in use.
Open vSwitch is used as the SDN-enabled component in the topology. It works with OpenFlow and allows flow rules to be installed for specific traffic-handling operations. In this project, the Open vSwitches are used to perform simple MPLS operations such as Push, Swap, and Pop.

As OpenFlow switches, the Open vSwitches require an SDN controller. The controller used in this project is OpenDaylight Carbon. OpenDaylight provides centralized control and communication with the Open vSwitches, while OpenFlow Manager is used to manage and inject OpenFlow rules through a graphical interface.

The entire lab is built and tested in GNS3, which provides the simulation environment for connecting the routers, Open vSwitches, and controller. Through this setup, the project demonstrates how traditional networking and SDN can work together in a hybrid model.
Overall, this project follows a service-based hybrid SDN approach because SDN is not used to replace the whole network. Instead, it is added as a programmable service layer to support selected MPLS operations, while the traditional network continues to provide stable routing and connectivity.

<img width="1672" height="941" alt="PrOJECT PROCESS" src="https://github.com/user-attachments/assets/dd7c5420-31d8-406c-9924-a067c178700f" />

# Flow Injection

The image below confirms that the Open vSwitches were discovered through LLDP, enabling the OpenDaylight controller to identify and display the network topology:

<img width="450" height="211" alt="Screenshot 2026-04-26 103405" src="https://github.com/user-attachments/assets/ebc95432-6642-433f-b926-4dd6334b73da" />

Subsequently, the command below was executed on the switch to verify its connection to the OpenDaylight controller:

<img width="348" height="211" alt="Screenshot 2026-04-26 103103" src="https://github.com/user-attachments/assets/1b344edc-cad5-4004-921a-370ef9a1eee9" />

This shows the flow rule injected through OpenFlow Manager on OVS1 to match incoming IP packets and encapsulate them with an MPLS label before forwarding them toward OVS2.

<img width="1672" height="941" alt="Screenshot 2026-04-05 1254521" src="https://github.com/user-attachments/assets/e46bafb4-5759-48c4-9b03-7a99533351a1" />


