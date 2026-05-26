<img width="400" height="38" alt="image" src="https://github.com/user-attachments/assets/9d13b387-4c16-42d1-ae3b-731b8692e100" /><h1>System Programming</h1>
<h3>Useful Links: </h3>
<ul>
  <li>https://medium.com/@boutnaru/the-linux-concept-journey-syscalls-system-calls-efcd7703e072</li>
</ul>

<h3>Command: </h3>
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
    <td><code>strace ./binary_name</code></td>
    <td>Provide details what all system calls a user space program is calling
        e.g strace ./a.out.</td>
  </tr>

  <tr>
    <td><code>strace -c ./binary_name</code></td>
    <td>Count  time,  calls, and errors for each system call and report a summary on program exit.</td>
  </tr>

  <tr>
    <td><code>strace -f -o strace.out bash silence_date.sh</code></td>
    <td>
      <ul>
        <li><b>-f(follow):</b>Track child processes. Since bash will fork a new process to run the date command, this is essential to see what date is doing.
        </li>
        <li><b>-o strace.out: </b>Save the massive amount of technical data to a file instead of flooding your terminal.
        </li>
      </ul>
    </td>
  </tr>

   <tr>
    <td><code>readelf -d binary_name</code></td>
    <td>Display list of all .so files on which the given binary is dependent.</td>
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
    <td><code>echo $$</code></td>
    <td>prints the Process ID (PID) of the current shell.<br>
    <ul>
      <li> $ is a special shell variable that always contains the PID of the shell instance you're running. </li>
      <li> echo $ simply outputs that number.</li>
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
    <td><code>!sudo</code></td>
    <td>Prepends sudo to your last command (e.g., sudo !!)</td>
  </tr>

  <tr>
    <td><code>!abc</code></td>
    <td>Re-runs the most recent command that started with "abc".</td>
  </tr>

  <tr>
    <td><code>!?abc?</code></td>
    <td>Re-runs the most recent command containing "abc" anywhere in the line.</td>
  </tr>

  <tr>
    <td><code>!n</code></td>
    <td>Re-runs a specific command line number n from your history list.</td>
  </tr>
  
  <tr>
    <td><code>!-n</code></td>
    <td>Last back nth executed cmd.</td>
  </tr>

  <tr>
    <td><code>$?</code></td>
    <td>Termination status of the last executed program!</td>
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

  <tr>
    <td>
      <pre><code>/lib/aarch64-linux-gnu/libc.so.6
      OR
      /lib/x86_64-linux-gnu/libc.so.6</code></pre>
    </td>
    <td>When we run the library as an executable, it displays various text, including its version number.</td>
  </tr>

  <tr>
    <td><code>pstree </code></td>
    <td>Display all running processes in a <b>hierarchical tree format.</b></td>
  </tr>

  <tr>
    <td><code>size binary_name</code></td>
    <td>Displays the size of the text, initialized data, and uninitialized data(bss) segments of a binary executable.</td>
  </tr>

  <tr>
    <td><code>printenv</code></td>
    <td>Displays the current environment variable list.</td>
  </tr>

  <tr>
    <td><code>mtrace</code></td>
    <td>mtrace is a GNU C Library (glibc) tool used to detect memory leaks in C programs. It tracks every malloc and free call to ensure they match up.
      <ol>
        <li><b>Modify your C code:</b><br>Include <mcheck.h> and call mtrace() at the start of main().</li>
        <li><b>	Set the envrinment variable:</b><br>
          <mark><b>LD_PRELOAD=/lib/aarch64-linux-gnu/libc_malloc_debug.so.0 MALLOC_TRACE=./mtrace.log ./mtrace_test</b></mark>
        </li>
        <li><b>Run the program with mtrace tool and log file.</b><br>
          <mark><b>mtrace ./mtrace_test ./mtrace.log(show the memleak in the process <mtrace_test here>)</b></mark>
        </li>
      </ol>
    </td>
  </tr>

  <tr>
    <td><code>ls /proc/PID/task | wc -l</code></td>
    <td>Count the threads in your process.</td>
  </tr>

  <tr>
    <td><code>top -H -p [PID]</td>
    <td>Find which thread is consuming the most CPU. (The -H flag instructs top to show individual threads).</td>
  </tr>

  <tr>
    <td><code>cat /proc/[PID]/task/[TID]/status</td>
    <td>Check the status of a specific thread.</td>
  </tr>

  <tr>
    <td><code>lsblk</td>
    <td>see all available block devices and identify your drive.</td>
  </tr>

  <tr>
    <td><code>head /proc/meminfo</code></td>
    <td>Running head /proc/meminfo gives you a raw, real-time snapshot of how your system is juggling memory.
      <br>Unlike the free command, which simplifies things, this file pulls data directly from the kernel's data structures.
      <b><mark>Breaking Down the Top 5 Lines:</mark></b>
      <ol>
        <li><b>MemTotal: </b>The total usable RAM (physical RAM minus a few reserved bits for the kernel).</li>
        <li><b>MemFree: </b>RAM that is completely untouched. Note: In Linux, a low number here is usually fine!</li>
        <li><b>MemAvailable: </b>This is the most important number.
          <br>It estimates how much memory is actually available for starting new applications without swapping.
          <br>It includes MemFree plus reclaimable caches.
        </li>
        <li><b>Buffers: </b>Temporary storage for raw disk blocks (waiting to be written to the drive).</li>
        <li><b>Cached: </b>The "Page Cache." Linux uses "empty" RAM to store files you've recently read, making the system feel much faster.</li>
      </ol>
    </td>
  </tr>

  <tr>
    <td><code>systemctl enable --now process_name</td>
    <td>It will start the process immediately.</td>
  </tr>

  <tr>
    <td><code>systemctl restart process_name</td>
    <td>Restart the process.</td>
  </tr>

  <tr>
    <td><code>curl [option] URL</td>
    <td>curl (short for "Client URL") is a powerful command-line tool used to transfer data to or from a server using various network protocols,
      <br>such as HTTP, HTTPS, FTP, and more. It is widely used by developers for testing APIs, downloading files, and automating web tasks
      <br>directly from the terminal.</td>
  </tr>

  <tr>
    <td><code>id</td>
    <td>Gives user details. If you see uid=0(root), you are logged in with root.</td>
  </tr>

  <tr>
    <td><code>ls -d</td>
    <td>list directories themselves, rather than listing the files inside those directories.</td>
  </tr>
      
</table>

<h3>Gdb commands: </h3>
<table>
  <tr>
    <th>Command</th>
    <th>Use</th>
  </tr>

  <tr>
    <td><code>info registers lr</code></td>
    <td>
      Return Address isn't always on the stack immediately;
      it's often stored in the <b>Link Register (lr or x30)</b>.
    </td>
  </tr>

  <tr>
    <td><code>x/3i $pc</code></td>
    <td>
      Show the next 3 instructions.
    </td>
  </tr>

  <tr>
    <td><code>x/i $pc</code></td>
    <td>
      You can see the exact assembly instruction at that spot by running this command.
    </td>
  </tr>

  <tr>
    <td><code>info registers pc</code></td>
    <td>
      Program Counter (PC) register info.
    </td>
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

  <tr>
    <td><code>/proc/sys/kernel/pid_max</code></td>
    <td>Process id max limit.</td>
  </tr>

  <tr>
    <td><code>/proc/[PID]/status</code></td>
    <td>It is a virtual file that provides a human-readable summary of the current status for the process with PID.</td>
  </tr>

  <tr>
  <td><code>/proc/&lt;PID&gt;/maps</code></td>
  <td>
    The Linux kernel generates a text-based representation of the
    <b>Virtual Memory Areas (VMAs)</b>.
  </td>
</tr>

<tr>
  <td><code>/proc/&lt;PID&gt;/cmdline</code></td>
  <td>
    The command-line arguments of any process can be read via this file.
  </td>
</tr>

<tr>
  <td><code>/proc/&lt;PID&gt;/environ</code></td>
  <td>
    Environment list of the process.
  </td>
</tr>

<tr>
  <td><code>/etc/fstab</code></td>
  <td>
    The <code>/etc/fstab</code> (file systems table) file is a system
    configuration file that contains information about all available disks
    and partitions and indicates how they should be automatically initialized
    or mounted into the system.
  </td>
</tr>

<tr>
  <td><code>/proc/&lt;PID&gt;/mounts</code></td>
  <td>
    Mount points for this process.
  </td>
</tr>

<tr>
  <td><code>/proc/PID/fd/</code></td>
  <td>
    The directory <code>/proc/[PID]/fd/</code> contains symbolic links to
    every file descriptor (FD) currently held open by that process.
    <br><br>
    FD 0: <b>Standard Input (stdin)</b><br>
    FD 1: <b>Standard Output (stdout)</b><br>
    FD 2: <b>Standard Error (stderr)</b>
  </td>
</tr>

<tr>
  <td><code>/proc/PID/task</code></td>
  <td>
    The <code>/proc/[PID]/task</code> directory contains a subdirectory
    for every <b>thread</b> currently belonging to that process.
    <br><br>
    <b>Structure</b><br>
    Inside <code>/proc/[PID]/task</code>, you will see folders named
    with TIDs (Thread IDs).
    <ul>
      <li>
        For a single-threaded program, there is only one folder,
        and its TID will match the PID.
      </li>
      <li>
        For multi-threaded programs (e.g., using
        <code>pthread_create</code>), you will see multiple folders.
      </li>
    </ul>
  </td>
</tr>

<tr>
  <td><code>include/uapi/asm-generic/unistd.h</code></td>
  <td>
    Information about system calls.
  </td>
</tr>

</table>

<h3>Flags: </h3>

<table>
  <tr>
    <th>Flag</th>
    <th>Use</th>
  </tr>

  <tr>
    <td><code>O_SYNC</code></td>
    <td>
      <b>O_SYNC</b> is a file status flag used with the
      <code>open()</code> system call to request
      <b>synchronous I/O</b>.
      <br><br>
      When you open a file with the <code>O_SYNC</code> flag,
      every <code>write()</code> operation becomes blocking.
      The system call returns only after:
      <ol>
        <li>
          The data has been physically written to the storage device
          (SSD/HDD).
        </li>
        <li>
          The file metadata (inode information such as modification
          time and file size) has also been updated on disk.
        </li>
      </ol>
    </td>
  </tr>

  <tr>
    <td><code>O_DSYNC</code></td>
    <td>
      <b>O_DSYNC</b> (Data Synchronous) is a performance-optimized
      version of <code>O_SYNC</code>.
      <br><br>
      While <code>O_SYNC</code> waits for both the
      <b>data</b> and the <b>metadata</b> to be written to disk,
      <code>O_DSYNC</code> waits only for the data itself.
      <br><br>
      <ul>
        <li>
          <b>O_SYNC:</b>
          "Don't return until the data and inode details are safe."
        </li>
        <li>
          <b>O_DSYNC:</b>
          "Don't return until the data is safe. Metadata updates can wait."
        </li>
      </ul>
    </td>
  </tr>

  <tr>
    <td><code>O_RSYNC</code></td>
    <td>
      <b>O_RSYNC</b> (Read Synchronous) provides synchronization
      guarantees for <code>read()</code> operations.
      <br><br>
      When used with <code>O_SYNC</code> or
      <code>O_DSYNC</code>, a <code>read()</code> call blocks
      until pending writes affecting that data are synchronized.
      <br><br>
      <ul>
        <li>
          <b>With O_DSYNC:</b>
          Read blocks until data and required metadata are synchronized.
        </li>
        <li>
          <b>With O_SYNC:</b>
          Read blocks until data and all metadata are synchronized.
        </li>
      </ul>
    </td>
  </tr>

  <tr>
    <td><code>O_DIRECT</code></td>
    <td>
      <b>O_DIRECT</b> is a Linux-specific <code>open()</code>
      flag used to bypass the kernel's <b>page cache</b>.
      <br><br>
      Data is transferred directly between the user-space buffer
      and the storage device using DMA (Direct Memory Access),
      without intermediate kernel buffering.
    </td>
  </tr>
</table>

<h3>Data structure: </h3>

<table>
  <tr>
    <th>Data structure / Macro / Function</th>
    <th>Type</th>
    <th>Header File</th>
    <th>Use</th>
  </tr>

  <tr>
    <td><code>vm_area_struct</code></td>
    <td>Structure</td>
    <td><code>include/linux/mm_types.h</code></td>
    <td>
      <code>vm_area_struct</code> is the fundamental structure used to manage a process's virtual memory.
      <br><br>
      <b>Key Components</b>
      <ul>
        <li><code>vm_start</code> and <code>vm_end</code> → Memory boundaries</li>
        <li><code>vm_page_prot</code> → Memory permissions</li>
        <li><code>vm_flags</code> → Region attributes</li>
        <li><code>vm_next</code> and <code>vm_prev</code> → Linked-list navigation</li>
        <li><code>vm_rb</code> → Red-Black tree node for fast lookup</li>
      </ul>
      Address belongs to VMA only if:
      <br>
      <code>vm_start &lt;= addr &lt; vm_end</code>
    </td>
  </tr>

  <tr>
    <td><code>mm_struct</code></td>
    <td>Structure</td>
    <td>-</td>
    <td>
      Describes the complete virtual address space of a process.
      <br><br>
      <b>Contains</b>
      <ul>
        <li><code>mmap</code> → Linked list of VMAs</li>
        <li><code>mm_rb</code> → Red-Black tree root</li>
        <li><code>pgd</code> → Page Global Directory</li>
        <li><code>start_code</code>, <code>end_code</code></li>
        <li><code>start_data</code>, <code>end_data</code></li>
        <li><code>start_brk</code>, <code>brk</code></li>
        <li><code>start_stack</code></li>
        <li><code>mm_users</code> → Shared-user counter</li>
      </ul>
    </td>
  </tr>

  <tr>
    <td><code>char *getenv(const char *name)</code></td>
    <td>Function</td>
    <td><code>stdlib.h</code></td>
    <td>
      Returns a pointer to the value of an environment variable.
    </td>
  </tr>

  <tr>
    <td><code>int putenv(char *string)</code></td>
    <td>Function</td>
    <td><code>stdlib.h</code></td>
    <td>
      Adds or modifies an environment variable.
    </td>
  </tr>

  <tr>
    <td>
      <code>int setenv(const char *name, const char *value, int overwrite)</code>
    </td>
    <td>Function</td>
    <td><code>stdlib.h</code></td>
    <td>
      Creates or updates an environment variable.
    </td>
  </tr>

  <tr>
    <td><code>int unsetenv(const char *name)</code></td>
    <td>Function</td>
    <td><code>stdlib.h</code></td>
    <td>
      Removes an environment variable.
    </td>
  </tr>

  <tr>
    <td><code>mtrace</code></td>
    <td>Function</td>
    <td><code>mcheck.h</code></td>
    <td>
      Tracks memory allocation calls to detect memory leaks and invalid frees.
    </td>
  </tr>

  <tr>
    <td><code>LD_PRELOAD</code></td>
    <td>Environment Variable</td>
    <td>-</td>
    <td>
      Forces the dynamic linker to load a specific shared library before others.
      Used for function interposition or hooking.
    </td>
  </tr>

  <tr>
    <td><code>alloca</code></td>
    <td>Function</td>
    <td><code>alloca.h</code></td>
    <td>
      Allocates memory directly on the stack frame instead of the heap.
    </td>
  </tr>

  <tr>
    <td><code>Utsname</code></td>
    <td>Structure</td>
    <td><code>sys/utsname.h</code></td>
    <td>
      Stores operating system identity information like hostname,
      kernel version, architecture, etc.
    </td>
  </tr>

  <tr>
    <td><code>getpwnam()</code></td>
    <td>Function</td>
    <td><code>&lt;pwd.h&gt;</code></td>
    <td>
      Retrieves user account information using username.
    </td>
  </tr>

  <tr>
    <td><code>struct dirent</code></td>
    <td>Structure</td>
    <td><code>&lt;dirent.h&gt;</code></td>
    <td>
      Represents a directory entry inside a directory stream.
    </td>
  </tr>

  <tr>
    <td><code>stat()</code></td>
    <td>Function / System Call</td>
    <td>
      <code>&lt;sys/stat.h&gt;</code><br>
      <code>&lt;sys/types.h&gt;</code><br>
      <code>&lt;unistd.h&gt;</code>
    </td>
    <td>
      Retrieves metadata information about a file.
    </td>
  </tr>

  <tr>
    <td><code>struct stat</code></td>
    <td>Structure</td>
    <td>
      <code>&lt;sys/types.h&gt;</code><br>
      <code>&lt;sys/stat.h&gt;</code><br>
      <code>&lt;unistd.h&gt;</code>
    </td>
    <td>
      Contains file metadata such as owner, size, inode, permissions, and timestamps.
    </td>
  </tr>

  <tr>
    <td>
      <code>size_t strcspn(const char *s, const char *reject)</code>
    </td>
    <td>Function</td>
    <td><code>&lt;string.h&gt;</code></td>
    <td>
      Returns the number of characters before the first matching rejected character.
    </td>
  </tr>

  <tr>
    <td><code>fsync(int fd)</code></td>
    <td>Function</td>
    <td><code>&lt;unistd.h&gt;</code></td>
    <td>
      Flushes file data and metadata to disk.
    </td>
  </tr>

  <tr>
    <td><code>fdatasync(int fd)</code></td>
    <td>Function</td>
    <td><code>&lt;unistd.h&gt;</code></td>
    <td>
      Flushes only file data and required metadata to disk.
    </td>
  </tr>

  <tr>
    <td><code>sync()</code></td>
    <td>Function</td>
    <td><code>&lt;unistd.h&gt;</code></td>
    <td>
      Flushes all pending filesystem buffers to disk.
    </td>
  </tr>

  <tr>
    <td>
      <code>int setvbuf(FILE *stream, char *buf, int mode, size_t size)</code>
    </td>
    <td>Function</td>
    <td><code>&lt;stdio.h&gt;</code></td>
    <td>
      Changes buffering mode of a file stream.
    </td>
  </tr>

  <tr>
    <td><code>void setbuf(FILE *stream, char *buf)</code></td>
    <td>Function</td>
    <td><code>&lt;stdio.h&gt;</code></td>
    <td>
      Simplified interface for controlling stream buffering.
    </td>
  </tr>

  <tr>
    <td>
      <code>void setbuffer(FILE *stream, char *buf, size_t size)</code>
    </td>
    <td>Function</td>
    <td><code>&lt;stdio.h&gt;</code></td>
    <td>
      Similar to <code>setbuf()</code> but allows custom buffer size.
    </td>
  </tr>

  <tr>
    <td><code>STDOUT_FILENO</code></td>
    <td>Constant</td>
    <td><code>&lt;unistd.h&gt;</code></td>
    <td>
      File descriptor constant for standard output.
    </td>
  </tr>

  <tr>
    <td><code>fileno(FILE *stream)</code></td>
    <td>Function</td>
    <td><code>&lt;stdio.h&gt;</code></td>
    <td>
      Returns the file descriptor associated with a FILE stream.
    </td>
  </tr>

  <tr>
    <td><code>fdopen(int fd, const char *mode)</code></td>
    <td>Function</td>
    <td><code>&lt;stdio.h&gt;</code></td>
    <td>
      Creates a FILE stream from an existing file descriptor.
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
  <td><code>API</code></td>
  <td>
    <b>Application Programming Interface</b>
  </td>
 </tr>

<tr>
  <td><code>IDT</code></td>
  <td>
    <b>Interrupt Descriptor Table</b>
  </td>
</tr>

<tr>
  <td><code>LDD</code></td>
  <td>
    <b>List Dynamic Dependency</b>
  </td>
</tr>

<tr>
  <td><code>fcntl</code></td>
  <td>
    <b>File Control</b>
  </td>
</tr>

<tr>
  <td><code>O_CLOEXEC</code></td>
  <td>
    <b>Close-on-Exec</b><br><br>
    It is a flag used when opening a file or setting its properties to
    ensure the file descriptor is automatically closed when the process
    performs an <code>exec()</code> call.
  </td>
</tr>

<tr>
  <td><code>NOCTTY</code></td>
  <td>
    <b>No Controlling TTY</b>
  </td>
</tr>

<tr>
  <td><code>a.out</code></td>
  <td>
    <b>Assembler Output</b>
  </td>
</tr>

<tr>
  <td><code>ELF</code></td>
  <td>
    <b>Executable and Linking Format</b>
  </td>
</tr>

<tr>
  <td><code>COFF</code></td>
  <td>
    <b>Common Object File Format</b>
  </td>
</tr>

<tr>
  <td><code>etext</code></td>
  <td>
    <b><mark>End of Text</b></mark><br>
    The first address after the program code (text segment).
  </td>
</tr>

<tr>
  <td><code>edata</code></td>
  <td>
    <b><mark>End of Data</b></mark></b><br><br>
    The first address after the initialized global/static variables (data segment).
  </td>
</tr>

<tr>
  <td><code>end</code></td>
  <td>
    <b><mark>End of BSS</mark></b><br><br>
    The first address after the uninitialized variables
    (bss segment). This is also the start of the Heap.
  </td>
</tr>

<tr>
  <td><code>PMMU</code></td>
  <td>
    <b>Paged Memory Management Unit</b><br><br>
    The PMMU translated each virtual memory address reference and advises
    the kernel of a page fault when a particular virtual memory address
    corresponds to a page that is not resident in RAM.
  </td>
</tr>

<tr>
  <td><code>PLT</code></td>
  <td>
    <b>Procedure Linkage Table</b><br><br>
    The PLT handles finding the real address of C library functions
    in RAM at runtime.
  </td>
</tr>

<tr>
  <td><code>lr</code></td>
  <td>
    <b>Link Register</b>
  </td>
</tr>

<tr>
  <td><code>NIS</code></td>
  <td>
    <b>Network Information Services</b>
  </td>
</tr>

<tr>
  <td><code>MBR</code></td>
  <td>
    <b>Master Boot Record</b><br><br>
    MBR is a legacy partitioning scheme located in the first sector
    (512 bytes) of a hard drive. It contains bootloader code and the
    partition table.
  </td>
</tr>

<tr>
  <td><code>GPT</code></td>
  <td>
    <b>GUID Partition Table</b><br><br>
    GPT is the modern partitioning standard that replaced MBR.
    <br><br>
    <b>Why GPT is better than MBR</b>
    <ul>
      <li>Supports disks larger than 2 TB.</li>
      <li>Allows many primary partitions.</li>
      <li>Stores backup partition tables for recovery.</li>
      <li>Uses CRC32 for integrity checking.</li>
    </ul>
    <b>Example</b><br>
    <code>gdisk -l /dev/nvme0n1</code>
  </td>
</tr>

<tr>
  <td><code>UEFI</code></td>
  <td>
    <b>Unified Extensible Firmware Interface</b><br><br>
    UEFI is modern firmware software that connects hardware to the OS
    and replaced BIOS.
    <br><br>
    <b>Advantages</b>
    <ul>
      <li>Fast booting</li>
      <li>Large drive support</li>
      <li>Secure Boot support</li>
      <li>Modern graphical interface</li>
    </ul>
    <b>Check UEFI Mode</b><br>
    <code>ls /sys/firmware/efi</code>
  </td>
</tr>

<tr>
  <td><code>BIOS</code></td>
  <td>
    Basic Input/Output System<br><br>
    <b>Legacy BIOS Boot Process</b>
    <ul>
      <li>BIOS searches for the MBR.</li>
      <li>The MBR contains bootloader code and partition table.</li>
      <li>BIOS loads the first sector into RAM and executes it.</li>
    </ul>
  </td>
</tr>

</table>

<h3>Questions:</h3>

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

<p style="font-size: 20px; color: red;">
  <b>Q: What is sysret?</b>
</p>

<p>
  <b>Ans:</b><mark>sysret:</mark>
  The sysret instruction is the high-speed hardware mechanism used in x86-64 systems to return from a system call (CPL 0) to user space (CPL 3).
  <b>Key Operations of sysret: </b><br>When the kernel executes sysret, the CPU performs the following actions in a single atomic step:
  <ul>
    <li><b>Restores Instruction Pointer: </b>It loads the next instruction address to execute (RIP) directly from the RCX register.</li>
    <li><b>Restores Processor Flags: </b>It restores the system flags (RFLAGS) from the R11 register.</li>
    <li><b>Switches Privilege Level: </b>It changes the CPU's current privilege level from Ring 0 (Kernel) back to Ring 3 (User).</li>
    <li><b>Updates Segment Selectors: </b>It loads the Code Segment (CS) and Stack Segment (SS) registers with fixed values derived from the <b> IA32_STAR Model-Specific Register(MSR)</b>.
</li>
  </ul>
</p>

<p style="font-size: 20px; color: red;">
  <b>Q: How kernel checks the page access belongs to a memory region the process is allowed to use?</b>
</p>

<p>
  <b>Ans:</b>When a <b>Page Fault</b> occurs (because the PTE is missing or invalid), the kernel doesn't immediately crash the program with a SIGSEGV.<br>
  Instead, it consults a secondary, higher-level map called the <b>Virtual Memory Areas (VMAs).</b><br>
  While the <b>Page Table</b> is used by the Hardware (CPU), the <b>VMA list</b> is used by the <b>Software (Kernel)</b> to know what the memory should look like.<br>
  When a process tries to access memory, the kernel validates it using two layers: <br>
  the <b>Page Table (Hardware level)</b> and the VMA (Software level). Here is the summary of how it checks for a "legal" access:
  <ul>
    <li><b>The Trigger: </b>The CPU tries to translate a virtual address using the <b>Page Table Entry (PTE)</b>.<br>
      If the PTE is missing or has incorrect permissions, a <b>Page Fault</b> is triggered, handing control to the kernel. The Linux Kernel - Memory Management.
    </li>
    <li><b>The VMA Lookup: </b> The kernel searches the process’s <b>Virtual Memory Areas (VMAs)</b><br>
      (a list of "allowed" memory regions like text, data, and stack) to see if the address falls within any valid range. The proc(5) man page -<b>/proc/[pid]/maps</b>
    </li>
    <li><b>Permission Verification: </b>If a VMA is found, the kernel compares the requested action (Read, Write, or Execute)<br>
      against the <b>VMA's permissions</b> (e.g., trying to write to a read-only text segment).</li>

    <li>We can see VMA detail in <b>/proc/[PID]/maps</b> file.</li>
  </ul>
</p>

