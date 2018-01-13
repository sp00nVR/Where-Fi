# Where-Fi

Purpose: 
  -Wireless IDS for triangulation of rouge APs and unknown STAs using a mesh network of 'Finder' nodes and a centralized management server.

# Components
Management server
  - Centralized data collection point for Finder nodes
  - NTP to ensure Finder nodes data collection remains in-sync
  - GUI to initiate AP/STA search
  - WIFI AP
  
Finder Nodes
  - 3x minimum required for deployment
  - Capture RX power level of searched AP/STA and sends to Management Server

# Conectivity:
  1. Finder nodes connect to Management Server AP via 802.11 (5GHz). 
  2. NTP time sync at connection
  3. Management server passes search request to Finder nodes
  4. Finder nodes disconnect and switch from managed-mode to monitor-mode.
  5. When target is located, Finder returns to managed-mode and reconnects to Management Server AP to transmit the data
  
# Plotting:
  - RX power value of target reported by Finder node is represented as a circle.
  - Intersecting points of target circles from all Finder nodes is used to determine approximate location of target.

# Auto-Calibration
  - During initial setup, 'Finder' nodes will beacon their location and capture RX power levels of other nodes in range. Using the same triangulation algorithm as target plotting, Node 1 will act as the root location with remaining nodes graphed by estimated distance from each node based on RX power level. 
