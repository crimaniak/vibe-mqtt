vibe-mqtt changelog
===================

#### v0.2.0
- Fix subscribe to go through session, not directly
- Fix unittest imports
- Fix #10 - check packetId usage in session
- Fix #18 - unsubscribe is not implemented
- Fix #4 - A way to block publish instead of throwing old messages
- Fix #19 - Dispatcher only works with session.front packet
- Fix #9 - Wait for ConnAck before sending pending messages
- Fix #13 - Maintain client session state
- Fix #12 - QoS 2 level support
- Fix #28 - allow more than 23B for client identifier
- Fix #29 - Acquiring writer of already owned connection
- Fix #26 - compilable with the new vibe-core
- Fix unsubscribe sending blank topics
- Fix possible recursion on sending Disconnect while connection is failing
- Added possibility to set size of send (queue of messages to be send) and inflight (queue of messages being currently handled) queues
- Added support to set KeepAlive interval for sending control packets to determine connection state with the broker (PingReq/PingResp)
- Various refactorings and optimizations
- Added safe attribute throughout the library
- Make compatible with vibe-0.8.0
- Added possibility to set reconnect interval in settings to enable autoreconnect

#### v0.1.8
- Fix #25 - 32bit platform type fix
- Fix unittest imports
- Fix subscribe to go through session, not directly
- Partial fix to be usable with vibe-0.8.0

#### v0.1.7
- Fix import in tests.d
- Make client.subscribe topics parameter const to allow receive immutable
- onDisconnect() added to detect client disconnection from broker

#### v0.1.6
- Remove repeated allocation of buffer in listener loop
- Clean read buffer before connect
- Check if TCPConnection is empty in listener loop
- Fix #6 - disconnect() hangs up then listener() fibre in different task

#### v0.1.5
- Remove assert from connected property to be able to check even if the connection is not set yet
- Use of vibe submodules

#### v0.1.4
- Fixes publishing QoS1 messages
- Fix imports for dmd-2.071

#### v0.1.3
- Fix assertion failure due to packet buffer filling up

#### v0.1.2
- Fix connecting with username / password
- Fix FixedRingBuffer.freeOnDestruct deprecation
- Fix default struct constructor warning

#### v0.1.1
##### New features
- Basic session state implemented (requirement for QoS1,2)
- Supports QoS1 packet handling (delivery retry still missing)

##### Bugs fixed
- Packet ID generator returns 0 on rollover - which is invalid
- Fix compilation error with dmd-2.068-b2
- Fix - set packet state when added to Session queue

#### v0.1.0
- Initial release
