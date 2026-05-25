<h1>System Programming</h1>
<h3>Useful Links: </h3>
<ul>
  <li>https://medium.com/@boutnaru/the-linux-concept-journey-syscalls-system-calls-efcd7703e072</li>
</ul>

<h3>Command</h3>
<table>
  <tr>
    <th>Command</th>
    <th>Description</th>
  </tr>

  <tr>
    <td>
      <pre><code>Objdump --source binary_name
    OR
    objdump -S binary_name</code></pre>
    </td>
    <td>Display source code mixed with assembly output.</td>
  </tr>

  <tr>
    <td><code>objdump -f binary_name</code></td>
    <td>Display file header.</td>
  </tr>

  <tr>
    <td><code>objdump -x binary_name</code></td>
    <td> Show all headers.</td>
  </tr>

  <tr>
    <td><code>objdump -d binary_name</code></td>
    <td> Shows assembly code of the executable.</td>
  </tr>

   <tr>
    <td><code>objdump -h binary_name</code></td>
    <td> Displays sections like .text, .data, .bss.</td>
  </tr>

   <tr>
    <td><code>objdump -t binary_name</code></td>
    <td> Shows functions, variables, symbols.</td>
  </tr>

  <tr>
    <td><code>objdump -s binary_name</code></td>
    <td> Displays raw contents (hex + ASCII).</td>
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
    <td><b>i : </b>case insensitive<br><b>r :</b>recursive<br><b>l :</b>list of file (instead of  matching line) <br><b>e.g:</b>grep -irl sys_read include  ---> search sys_read in include dir (recursive, case insensitive, list of files).</td>
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

  <tr>
    <td><code>!!</code></td>
    <td>Repeat last executed cmd.</td>
  </tr>

  <tr>
    <td><code>!$</code></td>
    <td>Take argument of the last cmd.</td>
  </tr>

  <tr>
    <td><code>!-n</code></td>
    <td>Last back nth executed cmd.</td>
  </tr>

  <tr>
    <td><code>dd</code></td>
    <td>The dd command in Linux is used for low-level copying and conversion of data. It is powerful and often used for disk operations.<br>
      <mark>dd is dangerous if used incorrectly:</mark>
      <ul>
        <li>It can overwrite disks and delete data permanently.</li>
        <li>Double-check if= and of= before running. </li>
      </ul>
      <b>e.g: </b>dd if=/dev/zero of=file.bin bs=1M count=10
      <b>It creates a file filled with zeros.</b>
      <ul>
        <li><b>if=/dev/zero: </b>Input source = infinite stream of zero bytes</li>
        <li><b>of=file.bin: </b>Output file = file.bin (will be created)</li>
        <li><b>bs=1M</b>Block size = 1 MB</li>
        <li><b>count=10 </b>Number of blocks = 10</li>
      </ul>
      <b>Result: </b>Creates a file named file.bin of size 10 MB
    </td>
  </tr>

  <tr>
    <td><code>date -d @timestamp </code></td>
    <td>It would convert the time stamp in human readable format. e.g if from log file timastap you want to convert.</td>
  </tr>
  
</table>

<h3>Files:</h3>
<table>
  <tr>
    <th>File</th>
    <th>Use/Description</th>
  </tr>

  <tr>
    <td><code>/etc/security/limits.conf</code></td>
    <td>Config file for resource limit. Set limits on system resources for users or groups.</td>
  </tr>

  <tr>
    <td><code>/dev/zero</code></td>
    <td>
      <ul>
        <li>/dev/zero is a pseudo‑device that produces an infinite stream of null bytes (\0) when read.</li>
        <li>Reading from /dev/zero returns:<br>00000000 00000000 00000000 00000000 ...</li>
      </ul>
    </td>
  </tr>
</table>

<h3>Abbreviation:</h3>
<table>
  <tr>
    <th>Abbreviation</th>
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
</table>

<h3>FAQ</h3>

<p style="font-size: 20px; color: red;">
  <b>Q: What's a core dump?</b>
</p>

<p>
  <b>Ans:</b> A core dump is a snapshot of certain dynamic regions (segments) of the process at the time it crashed (technically, it's a snapshot of minimally the data and stack segments). The core dump can be analyzed postmortem using debuggers such as GDB.
</p>

<p style="font-size: 20px; color: red;">
  <b>Q: How does the system know that this region is protected and what kind of protection it has?</b>
</p>

<p>
  <b>Ans:</b>These details are encoded into the Paging Table Entry (PTEs) for the process, and are checked by the MMU on every access!
</p>

<p style="font-size: 20px; color: red;">
  <b>Q: How dynamic library works?</b>
</p>

<p>
  <b>Ans:</b>
  <ol>
    <li><b>Program Startup.</b></li>
    	<b>When you run a dynamically linked executable:</b>
      <ul>
        <li> The kernel loads the executable's ELF header.</li>
        <li> It sees that the program is dynamically linked and hands control to the dynamic loader.</li>
      </ul>
    <li><b>Reading the ELF Headers</b></li>
      <b>The dynamic loader:</b>
      <ul>
        <li>Parses the ELF (Executable and Linkable Format) headers.</li>
        <li>Identifies all required shared libraries listed in the .dynamic section</li>
         <mark>readelf -d executable_name </mark> --> with this cmd you can see your elf is dependent on which all .so files.<br>OR<br><mark>ldd binary_name</mark>
      </ul>
    <li><b>Locating Libraries</b></li>
      <b>	It searches for each required library using:</b>
      <ul>
        <li><b>/etc/ld.so.cache:</b> A fast lookup cache.</li>
        <li><b>LD_LIBRARY_PATH: </b>Environment variable for custom paths.</li>
        <li><b>/etc/ld.so.conf:</b> Config file listing library directories.</li>
        <li><b>Default paths:</b> Like /lib, /usr/lib.</li>
      </ul>
    <li><b>Mapping Libraries into Memory</b></li>
      <b>Once found, each library is:</b>
      <ul>
        <li>Mapped into the process’s address space using mmap.</li>
        <li>The loader ensures that dependencies of libraries are also loaded.</li>
        <b><mark>e.g cat /proc/3393/maps | grep '.so' </b></mark>  --> 3393 is process pid.
          7f807a9000-7f807c8000 r-xp 00000000 103:23 2521    /usr/lib/libmnl.so.0.2.0
        <li>7f807a9000-7f807c8000: Start and end addresses of the memory region.</li>
        <li><b>r-xp:</b> Permissions:</li>
        <li><b>r:</b> readable</li>
        <li><b>w:</b>writable</li>
        <li><b>x:</b>executable</li>
        <li><b>p:</b>private (copy-on-write)</li>
        <li><b>00000000:</b>Offset into the file.</li>
        <li><b>103:23:</b>Device ID (major:minor).</li>
        <li><b>2521:</b>Inode number.</li>
        <li><b>/usr/lib/libmnl.so.0.2.0:</b>Path to the shared library.</li>
      </ul>
    <li><b>Relocation and Symbol Resolution</b></li>
      <b>The loader:</b>
      <ul>
        <li>Resolves symbol references (e.g., function names) using the Global Offset Table (GOT) and Procedure Linkage Table (PLT).</li>
        <li>Applies relocations so that function calls and variable accesses point to the correct memory addresses.</li>
      </ul>
    <li><b>Calling Initialization Functions</b></li>
        <b>Before handing control to main():</b>
        <ul>
          <li>The loader calls any initialization routines in the libraries (like __init functions or constructors in C++).</li>
        </ul>
    <li><b>Execution Begins</b></li>
        <ul>
          <li>Finally, control is passed to the program’s main() function, and execution begins with all libraries loaded and ready.</li>
        </ul>
  </ol>
</p>

<p style="font-size: 20px; color: red;">
  <b>Q: What is diff between cmd > /dev/null and cmd > /dev/null 2>&1 ?</b>
</p>

<p>
  <b>Ans:</b>
  <ul>
    <li>/dev/null hides only stdout.</li>
    <li>/dev/null 2>&1 hides both stdout and stderr</li>
  </ul>
  </p>

  <p style="font-size: 20px; color: red;">
  <b>Q: How cmd > /dev/null 2>&1 works?</b>
</p>

<p>
  <b>Ans:</b>
  <ul>
    <li><b>/dev/null: </b> Redirects stdout (file descriptor 1) of cmd to /dev/null (the “black hole”).</li>
    <li><b>2>&1: </b>Redirects stderr (file descriptor 2) to where stdout is currently going. Since you already sent stdout to /dev/null,  both stdout and stderr are suppressed.</li>
  </ul>
</p>

