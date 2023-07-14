---

layout: col-sidebar
title: OWASP eBPFShield
tags: example-tag
level: 2
type: 
pitch: A very brief, one-line description of your project

---

<h1 align="center">
 <a><img alt="cgapp logo" src="https://github.com/sagarbhure/certificates/blob/main/ebpf%20-%20Copy.PNG" width="284px"/></a> <br/>
  <p>Advanced IP-Intelligence & DNS Monitoring using eBPF</p>
</h1>
<p align="center"><b>🛡️ Advanced host monitoring and threat detection with eBPF 🛡️</b></p>

<p align="center"><b>eBPFShield</b> is a high-performance <b>security tool</b> that utilizes eBPF and Python to provide real-time <b>IP-Intelligence</b> and <b>DNS monitoring</b>. By executing in kernel space, eBPFShield avoids costly context switches and offers efficient <b>detection</b> and <b>prevention</b> of malicious behavior on your network through monitoring of outbound connections and comparison with <b>threat intelligence</b> feeds. 🔍 </p>
<div align='center'>
<a href='https://github.com/sagarbhure/eBPFShield/releases'>
  
<img src='https://img.shields.io/github/v/release/chroline/well_app?color=%23FDD835&label=version&style=for-the-badge'>
  
</a>
  
<a href='https://github.com/sagarbhure/eBPFShield/blob/main/LICENSE'>
  
<img src='https://img.shields.io/github/license/chroline/well_app?style=for-the-badge'>
</a>

</div>
<br/><br/>
<p align="left"><b>📝 Introduction</b></p>
Welcome to eBPFShield, a powerful and intuitive security tool for monitoring and protecting your servers. Featuring both <b>IP-Intelligence</b> and <b>DNS monitoring</b> capabilities, eBPFShield utilizes the power of ebpf and python to provide real-time monitoring and actionable insights for identifying and mitigating potential threats.

Say goodbye to constantly monitoring your servers with tcpdump and hello to a more efficient and automated security solution with eBPFShield.

**Available for ~~Windows~~, Linux and Ubuntu.**

**Feature Roadmap: 📅**

- Automated IP reputation analysis using **Machine Learning** algorithms
- Support for IPv6 and non-standard DNS ports for improved coverage and detection
- Advanced forensics support to support Fileless Execution, Illegitimate Shell, kernel module loading
- Integration with popular **SIEM** systems for centralized monitoring and alerting
- JSON output for easy integration with a **UI** dashboard
- Detection of DNS packets on non-standard ports

<br/><br/>
<p align="left"><b>🚀 Usage</b></p>
 Run `python main.py` to get started. Out of the box it will not take any action, it'll just print violations as it sees them.

```
$ python main.py -h
usage: main.py [-h] [--block {print, dump, suspend, kill}] [--feature {ebpf_ipintelligence, ebpf_monitor}] [--verbose]

optional arguments:
  -h, --help            show this help message and exit
  --block {print, dump, suspend, kill}
  --feature {ebpf_ipintelligence, ebpf_monitor, ml_ebpf, ebpf_antidebugging}
  --verbose

```

There are four options supported under `--features` flag:
  - `ebpf_ipintelligence`: monitor and block outbound connections against IP threat intelligence lists using tcp/udp and ipv4.
  - `ebpf_monitor`: displays all DNS queries in the system. 
  - `ml_ebpf`: runs decision tree on user/kernel space based on ebpf_wrapper
  - `ebpf_antidebugging`: Detect possible code injection into another process
  
There are four actions currently supported via the `--block` flag:
- `print`: the default action, just writes to the screen and that's it
- `suspend`: send a `SIGSTOP` to the process. This can be useful if you need to keep the process in a state where you can interact with it.
- `kill`: kill the process. This may be useful if all you want to do is immediately stop potentially malicious behavior.
- `dump`: suspend the process, take a core dump of it for forensics, and then kill it.

If you're interested in debugging, the `--verbose` flag may be useful to you. This tells the program to print all connections it sees, not just malicious ones.

