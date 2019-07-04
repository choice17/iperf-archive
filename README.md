# iPerf 3 user documentation

## GENERAL OPTIONS
* Command line option Description

<h2 id="3doc">iPerf 3 user documentation</h2>
<p><a href="https://iperf.fr/iperf-doc.php#3doc">See official website</a></p>
<table class="tableau">
  <tbody>
  <tr>
    <th colspan="2">GENERAL OPTIONS</th></tr>
  <tr>
    <th>Command line option</th>
    <th>Description</th></tr>
  <tr>
    <td id="3port"><strong>-p</strong>, --port <i><strong>n</strong></i></td>
    <td>The server port for the server to listen on and the client to connect 
      to. This should be the same in both client and server. Default is 5201.</td></tr>
  <tr>
    <td id="3cport"><strong>--cport</strong> <i><strong>n</strong></i></td>
    <td>Option to specify the client-side port. (new in iPerf 3.1)</td></tr>
  <tr>
    <td id="3format"><strong>-f</strong>, --format <i><strong>[kmKM]</strong></i></td>
    <td>A letter specifying the format to print bandwidth numbers in. 
      Supported formats are&nbsp; 
<pre>&nbsp;&nbsp;&nbsp; 'k' = Kbits/sec&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 'K' = KBytes/sec
&nbsp;&nbsp;&nbsp; 'm' = Mbits/sec&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 'M' = MBytes/sec</pre>
    The adaptive formats choose between kilo- and mega- as appropriate.</td></tr>
  <tr>
    <td id="3interval"><strong>-i</strong>, --interval <i><strong>n</strong></i></td>
    <td>Sets the interval time in seconds between periodic bandwidth, jitter, 
      and loss reports. If non-zero, a report is made every <i><strong>interval</strong></i> 
      seconds of the bandwidth since the last report. If zero, no periodic 
      reports are printed. Default is zero.</td></tr>
  <tr>
    <td id="3filname"><strong>-F</strong>, --file name</td>
    <td><strong>client-side:</strong> read from the file and write to the network, instead of using random data;<br />
        <strong>server-side:</strong> read from the network and write to the file, instead of throwing the data away.</td></tr>
  <tr>
    <td id="3affinity"><strong>-A</strong>, --affinity <i><strong>n/n,m-F</strong></i></td>
    <td>Set the CPU affinity, if possible (Linux and FreeBSD only). On both the client and server you can set the local affinity by
    using the n form of this argument (where n is a CPU number). In addition, on the client side you can override the server’s
    affinity for just that one test, using the n,m form of argument. Note that when using this feature, a process will only be bound
    to a single CPU (as opposed to a set containing potentialy multiple CPUs).</td></tr>
  <tr>
    <td id="3bind"><strong>-B</strong>, --bind <i><strong>host</strong></i></td>
    <td>Bind to <i><strong>host</strong></i>, one of this machine's addresses. For the client 
      this sets the outbound interface. For a server this sets the incoming 
      interface. This is only useful on multihomed hosts, which have multiple 
      network interfaces.</td></tr>
  <tr>
    <td id="3verbose"><strong>-V</strong>, --verbose</td>
    <td>give more detailed output</td></tr>
  <tr>
    <td id="3json"><strong>-J</strong>, --json</td>
    <td>output in JSON format</td></tr>
  <tr>
    <td id="3logfile"><strong>--logfile</strong> file</td>
    <td>send output to a log file. (new in iPerf 3.1)</td></tr>
  <tr>
    <td id="3debug"><strong>--d</strong>, --debug</td>
    <td>emit debugging output. Primarily (perhaps exclusively) of use to developers.</td></tr>
  <tr>
    <td id="3version"><strong>-v</strong>, --version</td>
    <td>Show version information and quit.</td></tr>
  <tr>
    <td id="3help"><strong>-h</strong>, --help</td>
    <td>Show a help synopsis and quit.</td></tr>

  <tr>
    <td class="lignevide" colspan="2"></td></tr>
  <tr>
    <th colspan="2">SERVER SPECIFIC OPTIONS</th></tr>
  <tr>
    <th>Command line option</th>
    <th>Description</th></tr>
  <tr>
    <td id="3server"><strong>-s</strong>, --server</td>
    <td>Run iPerf in server mode. (This will only allow one iperf connection at a time)</td></tr>
  <tr>
    <td id="3daemon"><strong>-D</strong>, --daemon</td>
    <td>Run the server in background as a daemon.</td></tr>
  <tr>
    <td id="3pidfile"><strong>-I</strong>, --pidfile<i><strong>file</strong></i></td>
    <td>write a file with the process ID, most useful when running as a daemon. (new in iPerf 3.1)</td></tr>

  <tr>
    <td class="lignevide" colspan="2"></td></tr>
  <tr>
    <th colspan="2">CLIENT SPECIFIC OPTIONS</th></tr>
  <tr>
    <th>Command line option</th>
    <th>Description</th></tr>
  <tr>
    <td id="3client"><strong>-c</strong>, --client <i><strong>host</strong></i></td>
    <td>Run iPerf in client mode, connecting to an iPerf server running on <i><strong>host</strong></i>.</td></tr>
  <tr>
    <td id="3sctp"><strong>--sctp</strong></td>
    <td>Use SCTP rather than TCP (Linux, FreeBSD and Solaris). (new in iPerf 3.1)</td></tr>
  <tr>
    <td id="3udp"><strong>-u</strong>, --udp</td>
    <td>Use UDP rather than TCP. See also the <a href="#3bandwidth">-b</a> option.</td></tr>
  <tr>
    <td id="3bandwidth"><strong>-b</strong>, --bandwidth <i><strong>n[KM]</strong></i></td>
    <td>Set target bandwidth to n bits/sec (default 1 Mbit/sec for UDP, unlimited for TCP). If there are multiple streams (-P flag),
    the bandwidth limit is applied separately to each stream. You can also add a ’/’ and a number to the bandwidth specifier.
    This is called "burst mode". It will send the given number of packets without pausing, even if that temporarily exceeds the specified bandwidth limit.</td></tr>
  <tr>
    <td id="3time"><strong>-t</strong>, --time <i><strong>n</strong></i></td>
    <td>The time in seconds to transmit for. iPerf normally works by repeatedly sending an array of <i><strong>len</strong></i> bytes for <i><strong>time</strong></i> seconds. 
      Default is 10 seconds. See also the <a href="#3len">-l</a>, <a href="#3blockcount">-k</a> and <a href="#3num">-n</a> options.</td></tr>
  <tr>
    <td id="3num"><strong>-n</strong>, --num <i><strong>n[KM]</strong></i></td>
    <td>The number of buffers to transmit. Normally, iPerf sends for 10 
      seconds. The -n option overrides this and sends an array of <i><strong>len</strong></i> 
      bytes <i><strong>num</strong></i> times, no matter how long that takes. See also the <a 
      href="#3len">-l</a>, <a href="#3blockcount">-k</a> and <a href="#3time">-t</a> options.</td></tr>
  <tr>
    <td id="3blockcount"><strong>-k</strong>, --blockcount <i><strong>n[KM]</strong></i></td>
    <td>The number of blocks (packets) to transmit. (instead of -t or -n) 
      See also the <a href="#3time">-t</a>, <a href="#3len">-l</a> and <a href="#3num">-n</a> options.</td></tr>
  <tr>
    <td id="3len"><strong>-l</strong>, --length <i><strong>n[KM]</strong></i></td>
    <td>The length of buffers to read or write. iPerf works by writing an 
      array of <i><strong>len</strong></i> bytes a number of times. Default is 128 KB for TCP, 8 KB for UDP.
      See also the <a href="#3num">-n</a>, <a href="#3blockcount">-k</a> and <a href="#3time">-t</a> options.</td></tr>
  <tr>
    <td id="3parallel"><strong>-P</strong>, --parallel <i><strong>n</strong></i></td>
    <td>The number of simultaneous connections to make to the server. Default is 1.</td></tr>
  <tr>
    <td id="3reverse"><strong>-R</strong>, --reverse</td>
    <td>Run in reverse mode (server sends, client receives).</td></tr>
  <tr>
    <td id="3window"><strong>-w</strong>, --window <i><strong>n[KM]</strong></i></td>
    <td>Sets the socket buffer sizes to the specified value. For TCP, this 
      sets the TCP window size. (this gets sent to the server and used on that side too)</td></tr>
  <tr>
    <td id="3mss"><strong>-M</strong>, --set-mss <i><strong>n</strong></i></td>
    <td>Attempt to set the TCP maximum segment size (MSS). The MSS is usually the MTU - 40 bytes for the TCP/IP header.
      For ethernet, the MSS is 1460 bytes (1500 byte MTU).</td></tr>
  <tr>
    <td id="3nodelay"><strong>-N</strong>, --no-delay</td>
    <td>Set the TCP no delay option, disabling Nagle's algorithm.
      Normally this is only disabled for interactive applications like telnet.</td></tr>
  <tr>
    <td id="3version4"><strong>-4</strong>, --version4</td>
    <td>only use IPv4.</td></tr>
  <tr>
    <td id="3version6"><strong>-6</strong>, --version4</td>
    <td>only use IPv6.</td></tr>
  <tr>
    <td id="3tos"><strong>-S</strong>, --tos <i><strong>n</strong></i></td>
    <td>The type-of-service for outgoing packets. (Many routers ignore the TOS 
      field.) You may specify the value in hex with a '0x' prefix, in octal with 
      a '0' prefix, or in decimal. For example, '0x10' hex = '020' octal = '16' 
      decimal. The TOS numbers specified in RFC 1349 are:&nbsp; 
<pre>&nbsp;&nbsp;&nbsp; IPTOS_LOWDELAY&nbsp;&nbsp;&nbsp;&nbsp; minimize delay&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0x10
&nbsp;&nbsp;&nbsp; IPTOS_THROUGHPUT&nbsp;&nbsp; maximize throughput&nbsp;&nbsp; 0x08
&nbsp;&nbsp;&nbsp; IPTOS_RELIABILITY&nbsp; maximize reliability&nbsp; 0x04
&nbsp;&nbsp;&nbsp; IPTOS_LOWCOST&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; minimize cost&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0x02</pre>
    </td></tr>
  <tr>
    <td id="3flowlabel"><strong>-L</strong>, --flowlabel <i><strong>n</strong></i></td>
    <td>Set the IPv6 flow label (currently only supported on Linux).</td></tr>
  <tr>
    <td id="3zerocopy"><strong>-Z</strong>, --zerocopy</td>
    <td>Use a "zero copy" method of sending data, such as sendfile(2), instead of the usual write(2). This uses much less CPU.</td></tr>
  <tr>
    <td id="3omit"><strong>-O</strong>, --omit <i><strong>n</strong></i></td>
    <td>Omit the first n seconds of the test, to skip past the TCP <a href="https://en.wikipedia.org/wiki/Slow-start" target="_blank">TCP slowstart</a> period.</td></tr>
  <tr>
    <td id="3title"><strong>-T, --title <i><strong>str</strong></i></strong></td>
    <td>Prefix every output line with this string.</td></tr>
  <tr>
    <td id="3congestion"><strong>-C</strong>, --linux-congestion <i><strong>algo</strong></i></td>
    <td>Set the <a href="https://en.wikipedia.org/wiki/TCP_congestion-avoidance_algorithm" target="_blank">congestion control algorithm</a> (Linux only for iPerf 3.0, Linux and FreeBSD for iPerf 3.1).</td></tr>
</tbody></table>
<p>See also <a href="https://github.com/esnet/iperf" target="_blank">https://github.com/esnet/iperf</a></p>

