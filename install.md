# Install Instructions

## Manual install from git

Assuming you have git, make and root privileges:

```bash
git clone --branch latest https://github.com/jsamr/bootiso.git
cd bootiso
make install
```

Check the [dependencies](#deps) section for a list of packages to install.
The Makefile install target installs bootiso, its man page and shell completions.
You can uninstall from the same directory as the install step with the following:

```bash
make uninstall
```

<a name="deps"></a>

## Dependencies

**bootiso** relies mainly on classic GNU and POSIX command line utilities, with the exception of the more recents **wimlib** and **jq**.

**bootiso** should also have a soft dependency on `mkfs.xxx` creation commands for
each supported filesystem. User will be invited to install the appropriate utility when the requested filesystem has no matching creation command.
However, for the sake of user comfort, it is recommended that package maintainers define a hard dependency on the following commands:

- `mkfs.ext{2,3,4}`
- `mkfs.fat`
- `mkfs.ntfs`

The corresponding packages in Arch Linux are **e2fsprogs**, **dosfstools** and **ntfs-3g**. Mandated dependencies are listed bellow.

<table>
  <thead>
    <tr>
      <th rowspan="2" style="text-align: left;">command</th>
      <th colspan="3">package</th>
    </tr>
    <tr>
      <th>Arch Linux</th>
      <th>Debian</th>
      <th>Red Hat</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left;">wimlib-imagex</td>
      <td>wimlib</td>
      <td>wimtools</td>
      <td>wimlib-utils</td>
    </tr>
    <tr>
      <td style="text-align: left;">extlinux</td>
      <td rowspan="2">syslinux</td>
      <td>extlinux</td>
      <td rowspan="2">syslinux</td>
    </tr>
    <tr>
      <td style="text-align: left;">syslinux</td>
      <td>syslinux</td>
    </tr>
    <tr>
      <td style="text-align: left;">getconf</td>
      <td>glibc</td>
      <td>libc-bin</td>
      <td>glibc</td>
    </tr>
    <tr>
      <td style="text-align: left;">tput</td>
      <td>ncurses</td>
      <td>ncurses-bin</td>
      <td>ncurses</td>
    </tr>
    <tr>
      <td style="text-align: left;">
        sfdisk
      </td>
      <td rowspan="2">util-linux &ge; 2.27</td>
      <td>fdisk <small>or util-linux &ge; 2.27<sup>1</sup></small></td>
      <td rowspan="2">util-linux &ge; 2.27</td>
    </tr>
    <tr>
      <td style="text-align: left;">
        blkid, blockdev, blockdev, column, eject, lsblk, mkfs, mount, partx, umount, wipefs
      </td>
      <td>util-linux &ge; 2.27</td>
    </tr>
    <tr>
      <td style="text-align: left;">bash</td>
      <td colspan="3" align="center">bash &ge; 4.0</td>
    </tr>
    <tr>
      <td style="text-align: left;">
        basename, cat, chmod, cut, date, dirname, md5sum, mkdir, sha1sum, sha256sum, sha512sum, sleep, tr, tty, <em>…etc</em>
      </td>
      <td colspan="3" align="center">coreutils</td>
    </tr>
    <tr>
    <tr>
      <td style="text-align: left;">strings</td>
      <td colspan="3" align="center">binutils</td>
    </tr> 
    <tr>
      <td style="text-align: left;">find, xargs</td>
      <td colspan="3" align="center">findutils</td>
    </tr>
    <tr>
      <td style="text-align: left;">jq</td>
      <td colspan="3" align="center">jq</td>
    </tr>
    <tr>
      <td style="text-align: left;">sed</td>
      <td colspan="3" align="center">sed</td>
    </tr>
    <tr>
      <td style="text-align: left;">grep</td>
      <td colspan="3" align="center">grep</td>
    </tr>
    <tr>
      <td style="text-align: left;">file</td>
      <td colspan="3" align="center">file</td>
    </tr>
    <tr>
      <td style="text-align: left;">awk</td>
      <td colspan="3" align="center">gawk</td>
    </tr>
    <tr>
      <td style="text-align: left;">rsync</td>
      <td colspan="3" align="center">rsync</td>
    </tr>
    <tr>
      <td style="text-align: left;">curl</td>
      <td colspan="3" align="center">curl</td>
    </tr>
    <tr>
      <td style="text-align: left;">tar</td>
      <td colspan="3" align="center">tar</td>
    </tr>
    <tr>
      <td style="text-align: left;">bc</td>
      <td colspan="3" align="center">bc</td>
    </tr>
  </tbody>
</table>

<sup>1</sup> **fdisk** has been shipped as a separate package for Debian since “Buster” (10.4) and Ubuntu “Bionic” (18.04).
