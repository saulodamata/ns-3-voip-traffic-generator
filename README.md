# ns-3-voip-traffic-generator

This is an implementation of a very simple VoIP Traffic Generator.

This code is kind of old (mid 2013). It's been a while since I was dealing with ns-3. So, I`m not sure if it is working with the most update versions of ns-3.


You have to put the files in the /src/applications/ directory:

voip-client-server-helper.(h/cc): /src/applications/helper/

voip-client.(h,cc) and voip-server.(h,cc): /src/applications/model/


Remember to add the entries for these files to the waf script (wscript).


To use this application in your simulation script:

VoipServerHelper voipServer (voipServerPort);
voipServer.SetAttribute ("Interval", TimeValue (voipPktInterval));
voipServer.SetAttribute ("PacketSize", UintegerValue (voipPktSize));
voipServerApps.Add (voipServer.Install (serverNode));
VoipClientHelper voipClient (remoteHostsInterfaces.GetAddress (ue), voipServerPort);
voipClientApps.Add (voipClient.Install (clientNode));

