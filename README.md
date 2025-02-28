# PacketFlow
PacketFlow alters the way the game communicates with the server to increase performance.  It cuts zoning times by over 3/4, and reduces dropped packets in instances by as much as 85%(real numbers vary with real conditions, it can be much less).  This is very easily detectable and while no adverse effects have yet been reported on retail servers, use at your own risk.  The plugin works as long as it is loaded, and can be loaded or unloaded at any time.  Due to potential for abuse, source code will not be released.

Slightly more technical explanation:
PacketFlow alters the method the game client uses to determine if it should send a packet.  This alteration will keep the S<>C flow in a 1:1 ratio, but reduce the minimum time, so it's benefits are limited by latency.  With low enough latency, it increases frequency of communication by up to 60%.  This does not result in the server sending any additional data besides packets that it would have otherwise discarded.  When zoning, the client naturally increases delay between packets by 2 seconds or more, then tapers it down to a more normal time period.  PacketFlow also prevents this after a connection is made to the new zone, allowing zone data to populate very quickly.


# Installation
1. Download the dll within the folder that matches your ashita version and interface.
2. Place the dll in your ashita/plugins folder.
3. Load with '/load PacketFlow' or add the same line to your startup script. PacketFlow is a plugin not an addon, so do not use '/addon load'.