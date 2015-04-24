Webtop README
=============

Relevant to version 1.11.2:

* Fixed column size issue with overview mode.

Based on dnstop, webtop reads either a live Ethernet stream or a pre-captured 
file of packets, and performs aggregations based on standard HTTP headers.

Below are the command-line options for webtop:

Input options:

  interface-name          The name of a Ethernet interface (eth1, etc.):
                          will need privileged access.
  -i=interface-name       Equivalent to just providing an unemcumbered Ethernet 
                          interface name.
  -i=/file/name           Name of a pre-captured packet file.
  -m file1 file2          Names of multiple pre-captured files

Output options:

  -o                      Send output to STDOUT (as opposed to live interface)
  -o=file                 Send output to file
  -of=output-view(s)      Set which view(s) to send to output
  -v=view-name            Set which view to use in live view mode; 
                          default to host

What to view:

   -f='BPF syntax'        Set a Berkeley Packet Filter
   -b='BPF syntax'        Same as -f, for those familiar with dnstop
   -F='HTTP header regex' Set only view if header data matches regex

How much to view:

   -c=packet-count        View a defined count of packets (### | ###k | ###M)
   -t=duration            View for a defined amount of time (### | ###m | ###h)

How often to view:

   -r=###                 : refresh rate; default 1 second

Available views:

  Live key command : Command-line view : Description
  s          : s       : SRC IP address
  d          : d       : DST IP address
  D          : sd      : SRC IP address / DST IP address
  g/G/Ctrl-G : g/sg/dg : GET/POST request (overall/by SRC IP/by DST IP)
  h/H/Ctrl-H : h/sh/dh : Host header (overall/by SRC IP/by DST IP)
  r/R/Ctrl-R : r/sr/dr : Referer header (overall/by SRC IP/by DST IP)
  a/A/Ctrl-A : a/sa/da : User-Agent header (overall/by SRC IP/by DST IP)
  l/L/Ctrl-L : l/sl/dl : Accept-Language header (overall/by SRC IP/by DST IP)
  n          : n       : AS Path name (requires GeoIPASNum2.csv file)
  e          : e       : GeoIP location (requires GeoIPCountryWhois.csv file)
  b/B        : sb/db   : Bits per second (by SRC IP / by DST IP)
  p/P        : sp/dp   : Packets per second (by SRC IP / by DST IP)


