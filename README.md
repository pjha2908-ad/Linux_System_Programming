# Linux_command

<table>
  <tr>
    <th>Command</th>
    <th>Description</th>
  </tr>

  <tr>
    <td><code>Objdump --source <binary_name></code></td>
    <td>To see assembly language code for the binary.</td>
  </tr>

  <tr>
    <td><code>ulimit -f</code></td>
    <td>To query the maximum possible size of files written to by the shell process.</td>
  </tr>

  <tr>
    <td><code>ulimit -a</code></td>
    <td>All resource limit. (It's per process not system-wide).</td>
  </tr>

  <tr>
    <td><code>ulimit -aS</code></td>
    <td>Display all Soft resource limit values.</td>
  </tr>

  <tr>
    <td><code>ulimit-aH</code></td>
    <td>Display all hard resource limit values.</td>
  </tr>

  <tr>
    <td><code>meld</code></td>
    <td>The meld command is used to compare and merge files or directories visually. It’s extremely handy for system programming, code reviews, config diffs, and resolving conflicts.</td>
  </tr>

  <tr>
    <td><code>grep -irl</code></td>
    <td><b>i : </b>case insensitive<br><b>r :</b>recursive<br><b>l :</b>list of file (instead of  matching line) <br><b>e.g:</b>bgrep -irl sys_read include  ---> search sys_read in include dir (recursive, case insensitive, list of files).</td>
  </tr>

  <tr>
    <td><code>Strace ./binary_name</code></td>
    <td>Provide details what all system calls a user space program is calling
        e.g strace ./a.out.</td>
  </tr>

   <tr>
    <td><code>readelf -d binary_name</code></td>
    <td>Display list of all .so files on which the given binary is dependent.</td>
  </tr>

   <tr>
    <td><code>echo $$</code></td>
    <td>prints the Process ID (PID) of the current shell.<br>
    <ul>
      <li> $ is a special shell variable that always contains the PID of the shell instance you're running. </li>
      <li> echo $ simply outputs that number.</li>
    </ul>
    </td>
  </tr>

  <tr>
    <td><code>grep ^b</code></td>
    <td>^b is a regular expression meaning:<br>
    <ul>
      <li> ^ → start of the lineg. </li>
      <li> b → the line must begin with the letter b.</li>
    </ul>
    </td>
  </tr>
  
</table>

<table>
  <tr>
    <th>File</th>
    <th>Use</th>
    <th>Use</th>
  </tr>

  <tr>
    <td><code>/etc/security/limits.conf</code></td>
    <td>Config file for resource limit</td>
  </tr>
  
<table>
  <tr>
    <th>Abreviation</th>
    <th>Description</th>
  </tr>
  
  <tr>
    <td><code>ISA</code></td>
    <td>Instruction Set Architecture</td>
  </tr>

  <tr>
    <td><code>OEM</code></td>
    <td>Original Equipment Manufacturers</td>
  </tr>

  <tr>
    <td><code>CPL</code></td>
    <td>Current Privilege Level</td>
  </tr>

  <tr>
    <td><code>ISR</code></td>
    <td>Interrupt service routine</td>
  </tr>

  <tr>
    <td><code>ISR</code></td>
    <td>Interrupt service routine</td>
  </tr>

  <tr>
    <td><code>PTE</code></td>
    <td>Page Table Entry</td>
  </tr>

  <tr>
    <td><code>COW</code></td>
    <td>Copy-On-Write</td>
  </tr>

  <tr>
    <td><code>KSM</code></td>
    <td>Kernel Samepage Merging</td>
  </tr>

  <tr>
    <td><code>TM</code></td>
    <td>Transcendent Memory</td>
  </tr>

  <tr>
    <td><code>ASLR</code></td>
    <td>Address Space Layout Randomization</td>
  </tr>

  <tr>
    <td><code>BSS</code></td>
    <td>Block Started by Symbol</td>
  </tr>

  <tr>
    <td><code>LIFO</code></td>
    <td>Last-In-First-Out</td>
  </tr>

  <tr>
    <td><code>IP</code></td>
    <td>Instruction Pointer</td>
  </tr>

  <tr>
    <td><code>(D)DoS</code></td>
    <td>(Distributed) denial-of-service </td>
  </tr>

  <tr>
    <td><code>USB</code></td>
    <td>Universal Serial Bus</td>
  </tr>

  <tr>
    <td><code>HDMI</code></td>
    <td>High Definition Multimedia Interface</td>
  </tr>

  <tr>
    <td><code>BIOS</code></td>
    <td>Basic Input Output System</td>
  </tr>

  <tr>
    <td><code>UEFI</code></td>
    <td>Unified Extensible Firmware Interface</td>
  </tr>

  <tr>
    <td><code>GPT</code></td>
    <td>GUID Partition Table</td>
  </tr>
