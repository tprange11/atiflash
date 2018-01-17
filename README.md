# atiflash
atiflash linux

source: https://bitcointalk.org/index.php?topic=1809527.0

wget https://github.com/d13g0s0uz4/atiflash/releases/download/0.1/atiflash_linux.tar.xz -O /tmp/atiflash_linux.tar.xz && sudo tar xvf /tmp/atiflash_linux.tar.xz -C /usr/local/bin/

sudo atiflash -i


--- ATIFLASH v4.25 ---
-h, -?, /h, /?          Help (this screen)

Format: ATIFLASH [command] [parameter1] [parameter2] [parameter3] <option/s>
[command]:
-i [Num]                Display information of ATI adapters in the system.
                        Display information of adapter [Num] if specified.
-ai [Num]               Display advanced information of ATI adapters on system.
                        Display advanced information of adapter [Num]
                        if specified.
-biosfileinfo <File>    Displays the Bios info in file <file>
-p <Num> <File>         Write BIOS image in file <File> to flash ROM in Adapter
                        <Num>.
-pa <File>              Write BIOS image <File> to all appropriate adapters.
-s <Num> <File> [Size]  Save BIOS image from adapter <Num> to file <File>.
                        First [Size] kbytes (except for Theater in bytes) of ROM
                        content is saved if [Size] is specified.
-cf <File> [Size] [Sum] Calculate 16-bit checksum for file <File>.
                        Checksum for the first [Size] kbytes of the file is
                        calculated if [Size] is specified.
-cb <Num> [Size] [Sum]  Calculate 16-bit BIOS image checksum for adapter <Num>.
                        Checksum for the first [Size] kbytes of the ROM content
                        is calculated if [Size] is specified.
-cr <Num> [Size] [Sum]  Calculate 16-bit ROM checksum for adapter <Num> and
                        compare it to the [Sum] specified.  This command is
                        the same as -cb if [Size] is specified.
-t <Num>                Test ROM access of adapter <Num>
-v <Num> <File>         Compare ROM content of adapter <Num> to <File>
-mi <Num> [ID]          Modify SSID & SVID in BIOS image of adapter <Num> to
                        <ID>.  SSID & SVID in BIOS image of adapter <Num> is
                        displayed if [ID] is not specified.
-mb <Num> <File>        Modify SSID, SVID, BIOS Pin Number, & Boot Message in
                        BIOS image of adapter <Num> to values in <filename>.
                        Input file example:
                           ssid = 715B
                           svid = 1002
                           biospn = "113-xxxxxx-xx"
                           bootmsg = "ATI graphic board"
-pak <File>             Package an executable for BIOS update according to
                        the commands in <File>.
                        Config file example:
                           outfile = update.exe
                           banner = "Update v1.0"
                           infile = a123.bin
                           command = -pa -padevid=715B infile
-isr <Num> <Build Number> <Board Number>  Set ISR number based on the given
                                          build and board number
                                          if not specified, print out ISR Number
-prod <Num> <12 digit serial number>      Set PROD number based
                                          on the given serial number
                                          if not specified, print out SN Number
-checkprodsn <Num> <12 Digit Serial Number>  Comparing the Prod SN based on 
                                             existing prod sn saved in ROM 

<option/s>:
-f              Force flashing regardless of security checkings (e.g. AsicID &
                BIOS file info check OR boot-up card).
-fa             Force flashing bypassing already-programmed check.
-fm             Force flashing bypassing BIOS memory config check.
-fs             Force flashing bypassing BIOS SSID check.
-fp             Force flashing bypassing BIOS P/N check.
-nw             No user interaction on test failure. 
-sst            Use SST25VFxxx flashing algorithm regardless of ROMID straps.
-st             Use ST M25Pxx flashing algorithm regardless of ROMID straps.
-atmel          Use AT25Fxxx flashing algorithm regardless of ROMID straps.
-nopci          Do not enumerate PCI adapters, i.e. enumerate only AGP and
                PCIe adpaters
-pcionly        Enumerate only PCI adapters, i.e. do not enumerate AGP and
                PCIe adapters
-agp            Enumerate only AGP adapters, i.e. do not enumerate PCI and
                PCIe adapters unless used with -pcie or -pci
-noagp          Do not enumerate AGP adapters, i.e. enumerate only PCI and
                PCIe adpaters
-pcie           Enumerate only PCIe adapters, i.e. do not enumerate AGP and
                PCI adapters unless used with -agp or -pci
-nopcie         Do not enumerate PCIe adapters, i.e. enumerate only AGP and
                PCI adpaters

-pci            Enumerate only PCI adapters, i.e. do not enumerate AGP and
                PCIe adapters unless used with -agp or -pcie
-noremap        Skip BARs error detection and remapping in PCI configuration
                space
-reboot         Force a reboot of the system after successfully completing the
                specified operation
-keepisrsn      keep the ISR Number on the adapter when flashing a new VBIOS
-keepprodsn     keep the Prod SN on the adapter when flashing a new VBIOS
-siireset       Specifies the GPIO Pin to be used as the Reset when updating
                SiI1930 microcontroller firmware
                Input example:
                   -siireset=7 <No Spaces>
-siiuprog       Specifies the GPIO Pin to be used as the uprog when updating
                SiI1930 microcontroller firmware
                Input example:
                   -siiuprog=14 <No Spaces>
-scansii        Overrides normal adapter detection to enable detecting SSI
                roms with/without TPI firmware
-log            Logs output to atiflash.log, overrides existing file
-logappend      Logs and appends output to atiflash.log
-ddc            Enable DDC support
-padevid=<ID>   Use with -pa command to update adapters of specific device ID.
-passid=<ID>    Use with -pa command to update adapters of specific SSID.
-pasvid=<ID>    Use with -pa command to update adapters of specific SVID.
-pavbpn=<VBPN>  Use with -pa command to update adapters of specific VBIOS PN.
-excl_memtrain_dtable     When flashing on new VBIOS, a pre-determined memory
                          training data table in the old VBIOS will not be
                          overwritten.
-isr <adapter num> [build num] [board num]     If build number and board number
                                               are specified, sets the ISR Number
                                               value in specified adapter.
                                               If only adapter is specified, the current
                                               ISR Number is displayed
-checkpn <adapter num> <filename>              Checks PN of the current product
                                               and compares it to external file
*<Num> = adapter number, <File> = filename
*[Size] = data block size in KBytes, except for Theater Pro in Bytes
*Use command -i to see the adapter numbers in the system.
*Theater Pro supports commands -i, p, s, cf, cr, t, v and options -f, -noremap.
