cConfiguration Examples

BNC comes with a number of configuration examples which can be used on all
operating systems. Copy the complete directory 'Example_Configs' which comes
with the software including sub-directories 'Input' and 'Output' to your disc.
There are several ways to start BNC using one of the example configurations:

* On graphical systems (except for Mac systems) you may use the computer mouse
  to 'drag' a configuration file icon and 'drop' it on top of BNC's program icon.

* You could also start BNC using a command line for naming a specific
  configuration file (suggested e.g. for Mac systems):
  bnc --conf <configFileName>

* On non-graphical systems or when running BNC in batch mode in the background
  you may start the program using a command line with a configuration file
  option in 'no window' mode (example for Windows systems):
  bnc.exe --conf <configFileName> --nw

Although it's not a must, we suggest that you always create BNC configuration
files with the filename extension '.bnc'.

We furthermore suggest for convenience reasons that you configure your system
to automatically start BNC when you double-click a file with the filename
extension '.bnc'. The following describes what to do on Windows systems to
associate the BNC program to such configuration files:


1. Right-click a file that has the extension '.bnc' and then click 'Open'. If
   the 'Open' command is not available, click 'Open With' or double-click the
   file.

2. Windows displays a dialog box that says that the system cannot open this
   file. The dialog box offers several options for selecting a program.

3. Click 'Select the program from a list', and then click 'OK'.

4. The 'Open With' dialog box is displayed. Click 'Browse', locate and then
   click the BNC program, and then click 'Open'.

5. Click to select the 'Always use the selected program to open this kind
   of file' check box.

6. Click 'OK'.

Some of the presented example configuration files contain a user ID 'Example'
with a password 'Configs' for accessing a few GNSS streams from public Ntrip
Broadcasters. This generic account is arranged for convenience reasons only.
Please be so kind as to replace the generic account details as well as the
place holders 'User' and 'Pass' by the personal user ID and password you
receive following an online registration through
http://register.rtcm-ntrip.org.

Note that the account for an Ntrip Broadcaster is usually limited to
pulling a specified maximum number of streams at the same time. As running
some of the example configurations requires pulling several streams, it
is suggested to make sure that you don't exceed your account's limits.

Make also sure that sub-directories 'Input' and 'Output' which are part of
the example configurations exist on your system or adjust the affected
example configuration options according to your needs.

Some BNC options require antenna phase center variations as made available
from IGS through so-called ANTEX files at ftp://igs.org/pub/station/general.
An example ANTEX file 'igs14.atx' is part of the BNC package for convenience.

The example configurations assume that no proxy protects your BNC host.
Should a proxy be operated in front of BNC then you need to introduce its
name or IP and port number in the 'Network' panel.

(A) Working with Configuration Files

You should be able to run all configuration file examples without changing
contained options. However, configurations 'Upload.bnc' and 'UploadPPP.bnc' are
exceptions because they require an input stream from a connected network engine.

1. Configuration File 'RinexObs.bnc'
Purpose: Convert RTCM streams to RINEX Observation files. The configuration
pulls streams from Ntrip Broadcasters using Ntrip Version 1 to generate 15min
1Hz RINEX Version 3 Observation files. See
http://igs.bkg.bund.de/ntrip/observations for observation stream resources.
目的：将RTCM流转换为RINEX观测文件。配置
使用Ntrip版本1从Ntrip广播机提取流以生成15分钟
1Hz RINEX版本3观测文件。看到了吗
http://igs.bkg.bund.de/ntrip/observations用于观测流资源。


2. Configuration File 'RinexEph.bnc'
Purpose: Convert a RTCM stream with navigation messages to RINEX Navigation
files. The configuration pulls a RTCM Version 3 stream with Broadcast Ephemeris
coming from the real-time EUREF and IGS networks and saves hourly RINEX Version
3 Navigation files. See http://igs.bkg.bund.de/ntrip/ephemeris for further
real-time Broadcast Ephemeris resources.
目的：将带有导航消息的RTCM流转换为RINEX导航
文件夹。该配置提取具有广播星历的RTCM版本3流
来自实时EUREF和IGS网络，节省每小时一次的RINEX版本
3个导航文件。看到了吗http://igs.bkg.bund.de/ntrip/ephemeris进一步
实时广播星历资源。

3. Configuration File 'BrdcCorr.bnc'
Purpose: Save Broadcast Corrections from RTCM SSR messages in hourly plain
ASCII files. See http://igs.bkg.bund.de/ntrip/orbits for various real-time IGS
or EUREF orbit/clock correction products.
目的：将RTCM SSR消息中的广播更正保存为每小时一次
ASCII文件。看到了吗http://igs.bkg.bund.de/ntrip/orbits用于各种实时IGS
或EUREF轨道/时钟校正产品。

4. Configuration File 'RinexConcat.bnc'
Purpose: Concatenate several RINEX Version 3 files to produce one compiled file
and edit the marker name in the file header. The sampling interval is set to 30
seconds. See section 'RINEX Editing & QC' in the documentation for examples on
how to call BNC from command line in 'no window' mode for RINEX file editing,
concatenation and quality check.
目的：连接多个rinexversion3文件以生成一个编译文件
并编辑文件头中的标记名。采样间隔设置为30
秒。参见文档中的“RINEX编辑和质量控制”一节，了解有关
如何在“无窗口”模式下从命令行调用BNC进行RINEX文件编辑，
连接和质量检查。

5. Configuration File 'RinexQC.bnc'
Purpose: Check the quality of a RINEX Version 3 file by means of a multipath
analysis. Results are saved on disk in terms of a plot in PNG format. See
section 'RINEX Editing & QC' in the documentation for examples on how to call
BNC from command line in 'no window' mode for RINEX file editing, concatenation
and quality check.
目的：通过多路径检查RINEX版本3文件的质量
分析。结果以PNG格式的绘图形式保存在磁盘上。看到了吗
文档中的“RINEX编辑和质量控制”部分提供了如何调用的示例
命令行中的“无窗口”模式下的BNC，用于RINEX文件编辑、连接
以及质量检查。


6. Configuration File 'RTK.bnc'
Purpose: Feed a serial connected receiver with observations from a nearby
reference station for conventional RTK. The stream is scanned for RTCM
messages. Message type numbers and latencies of incoming observations are
reported in BNC's logfile.
目的：为串行连接的接收器提供附近的观测数据
常规RTK的参考站。对流进行RTCM扫描
信息。消息类型编号和传入观察的延迟是
在BNC的日志文件中报告。

7. Configuration File 'FeedEngine.bnc'
Purpose: Feed a real-time GNSS engine with observations from remote reference
stations. The configuration pulls a single stream from an Ntrip Broadcaster.
You could also pull several streams from different casters. Incoming
observations are decoded, synchronized, output through a local IP port and also
saved into a file. Failure and recovery thresholds are specified to inform
about outages.
目的：为实时GNSS引擎提供来自远程参考的观测数据
车站。该配置从Ntrip广播机提取单个流。
你也可以从不同的施法者那里拉几个流。进来的
观测数据通过本地IP端口进行解码、同步和输出，并且
保存到文件中。指定故障和恢复阈值以通知
关于停电。

8. Configuration File 'PPP.bnc'
Purpose: Precise Point Positioning from observations of a rover receiver. The
configuration reads RTCM Version 3 observations, a Broadcast Ephemeris stream
and a stream with Broadcast Corrections. Positions are saved in the logfile.
目的：通过对月球车接收器的观测进行精确的点定位。这个
配置读取RTCM版本3观测，广播星历流
和一个有广播修正的流。位置保存在日志文件中。

9. Configuration File 'PPPNet.bnc'
Purpose: Precise Point Positioning for several rovers or receivers from an
entire network of reference stations in one BNC job. The possible maximum
number of PPP solutions per job depends on the processing power of the hosting
computer. This example configuration reads two RTCM Version 3 observation
streams, a Broadcast Ephemeris stream and a stream with Broadcast Corrections.
PPP Results for the two stations are saved in PPP logfiles.
用途：从同一个位置对多个探测器或接收器进行精确的点定位
一个BNC作业中的整个参考站网络。可能的最大值
每个作业的PPP解决方案数取决于主机的处理能力
计算机。此示例配置读取两个RTCM版本3
流、广播星历流和具有广播校正的流。
两个站点的PPP结果保存在PPP日志文件中。

10. Configuration File 'PPPQuickStart.bnc'
Purpose: Precise Point Positioning in Quick-Start mode from observations of a
static receiver with precisely known position. The configuration reads RTCM
Version 3 observations, Broadcast Corrections and a Broadcast Ephemeris stream.
Positions are saved in NMEA format on disc. They are also output through IP
port for real-time visualization with tools like RTKPLOT. Positions are saved
in the logfile.
目的：在快速启动模式下，通过对目标的观测进行精确的点定位
具有精确已知位置的静态接收器。配置读取RTCM
版本3观测，广播修正和广播星历流。
位置以NMEA格式保存在光盘上。它们也通过IP输出
使用RTKPLOT等工具进行实时可视化的端口。位置已保存
在日志文件里。

11. Configuration File 'PPPPostProc.bnc'
Purpose: Precise Point Positioning in post processing mode. BNC reads RINEX
Version 3 Observation and 3 Navigation files and a Broadcast Correction file.
PPP processing options are set to support the Quick-Start mode. The output is
saved in a specific post processing logfile and contains coordinates derived
over time following the implemented PPP filter algorithm.

12. Configuration File 'PPPGoogleMaps.bnc'
Purpose: Track BNC's point positioning solutions using Google Maps or
OpenStreetMap as background. BNC reads a RINEX Observation file and a RINEX
Navigation file to carry out a 'Standard Point Positioning' solution in post
processing mode. Although this is not a real-time application it requires the
BNC host to be connected to the Internet. Specify a computation speed, then hit
button 'Open Map' to open the track map, then hit 'Start' to visualize receiver
positions on top of GM/OSM maps.

13. Configuration File 'SPPQuickStartGal.bnc'
Purpose: Single Point Positioning in Quick-Start mode from observations of a
static receiver with quite precisely known position. The configuration uses
GPS, GLONASS and Galileo observations and a Broadcast Ephemeris stream.
目的：在快速启动模式下，通过对目标的观察进行单点定位
位置精确的静态接收器。配置使用
GPS、GLONASS和伽利略观测以及广播星历流。

14. Configuration File 'SaveSp3.bnc'
Purpose: Produces SP3 files from a Broadcast Ephemeris stream and a Broadcast
Correction stream. The Broadcast Correction stream is formally introduced in
BNC's 'Combine Corrections' table. Note that producing SP3 requires an ANTEX
file because SP3 file content should be referred to CoM.

15. Configuration File 'Sp3ETRF2000PPP.bnc'
Purpose: Produce SP3 files from a Broadcast Ephemeris stream and a stream
carrying ETRF2000 Broadcast Corrections. The Broadcast Correction stream is
formally introduced in BNC's 'Combine Corrections' table. The configuration
leads to a SP3 file containing orbits also referred to ETRF2000. Pulling in
addition observations from a reference station at precisely known ETRF2000
position allows comparing an 'INTERNAL' PPP solution with a known ETRF2000
reference coordinate.
目的：从广播星历流和流生成SP3文件
携带ETRF2000广播修正。广播校正流是
在BNC的“合并更正”表中正式引入。配置
导致SP3文件包含轨道（也称为ETRF2000）。拉入
从精确已知ETRF2000的参考站进行的附加观测
位置允许将“内部”PPP解决方案与已知的ETRF2000进行比较
参考坐标。


16. Configuration File 'Upload.bnc'
Purpose: Upload orbits and clocks from a real-time GNSS engine to an Ntrip
Broadcaster. For that the configuration reads precise orbits and clocks in
RTNET format. It also reads a stream carrying Broadcast Ephemeris. BNC converts
the orbits and clocks into Broadcast Corrections and encodes them to RTCM
Version 3 SSR messages to finally upload them to an Ntrip Broadcaster. The
Broadcast Correction stream is referred to satellite Antenna Phase Center (APC)
and reference system IGS14. Orbits are saved on disk in SP3 format and clocks
are saved in Clock RINEX format.
目的：将轨道和时钟从实时GNSS引擎上传到Ntrip
广播员。因此，配置读取精确的轨道和时钟
RTNET格式。它还读取一条流，其中载有广播星历。BNC转换
轨道和时钟转换成广播修正，并将它们编码为RTCM
版本3 SSR消息最终上传到Ntrip广播公司。这个
广播校正流被称为卫星天线相位中心（APC）
以及参考系统IGS14。轨道以SP3格式和时钟保存在磁盘上
以时钟RINEX格式保存。

17. Configuration File 'Combi.bnc'
Purpose: Pull several streams carrying Broadcast Corrections and a Broadcast
Ephemeris from an Ntrip Broadcaster to produce a combined Broadcast Correction
stream. BNC encodes the combination product in RTCM Version 3 SSR messages and
uploads that to an Ntrip Broadcaster. The Broadcast Correction stream is
referred to satellite Antenna Phase Center (APC) and not to satellite Center of
Mass (CoM). Its reference system is IGS14. Orbits are saved in SP3 format
(referred to CoM) and clocks in Clock RINEX format.

18. Configuration File 'CombiPPP.bnc'
Purpose: This configuration equals the 'Combi.bnc' configuration. However, the
combined Broadcast Corrections are in addition used for an 'INTERNAL' PPP
solutions based on observations from a static reference station with known
precise coordinates. This allows a continuous quality check of the combination
product through observing coordinate displacements.

19. Configuration File 'UploadEph.bnc'
Purpose: Pull a number of streams from reference stations to get hold of
contained Broadcast Ephemeris messages. They are encoded to RTCM Version 3
format and uploaded for the purpose of providing a Broadcast Ephemeris stream
with an update rate of 5 seconds.

20. Configuration File 'CompareSp3.bnc'
Purpose: Compare two SP3 files to calculate RMS values for orbit and clock
differences. GPS satellite G05 and GLONASS satellite R18 are excluded from this
comparison. Comparison results are saved in a logfile.

21. Configuration File 'Empty.bnc'
Purpose: Provide an empty example configuration file for BNC which only
contains the default settings.

(B) Working with Command Line configuration options

The following configuration examples make use of BNC's 'Command Line Interface'
(CLI). Configuration options are exclusively specified via command line. No
configuration file is used. Examples are provided as shell scripts for a Linux
system. They call BNC in 'no window' batch mode (command line option -nw).
The scripts expect 'Example_Configs' to be the current working directory.

22. Shell Script 'RinexQC.sh'
Purpose: Equals configuration file example 'RinexQC.bnc', checks the quality of
a RINEX Version 3 file by means of a multipath analysis. Virtual X-Server
'Xvfb' is operated while producing plot files in PNG format. BNC is offline.
All results are saved on disk.

23. Shell Script 'RinexConcat.sh'
Purpose: Equals configuration file example 'RinexConcat.bnc', concatenates
several RINEX Version 3 files to produce one compiled file and edit the marker
name in the file header. The sampling interval is set to 30 seconds. BNC is
offline.

24. Shell Script 'RinexEph.sh'
Purpose: Equals configuration file example 'RinexEph.bnc', converts a RTCM
stream with navigation messages to RINEX Navigation files. The configuration
pulls a RTCM Version 3 stream with Broadcast Ephemeris coming from the
real-time EUREF and IGS networks and saves hourly RINEX Version 3 Navigation
files. BNC runs online until it's terminated after 10 seconds.  See
http://igs.bkg.bund.de/ntrip/ephemeris for further real-time Broadcast
Ephemeris resources.

25. Shell Script 'ScanLate.sh'
Purpose: Scan an observation stream for contained RTCM message types, print
observation latencies. The output is saved in a logfile. Latencies are
reported every 10 seconds. BNC runs online until it's terminated after 20
seconds.

26. Shell Script 'RinexObs.sh'
Purpose: Equals configuration file example 'RinexObs.bnc', converts RTCM
streams to RINEX Observation files. The configuration pulls streams from two
Ntrip Broadcasters using Ntrip Version 1 to generate 15min 1Hz RINEX Version 3
Observation files. See http://igs.bkg.bund.de/ntrip/observations for
observation stream resources. BNC runs online until it's terminated after 30
seconds.

(C) Command Line configuration options overwriting Configuration File options

For specific applications you may like to use your own set of standard
configuration options from a configuration file and update some of its content
via command line. When using a configuration file and command line configuration
options together in one BNC call, the command line configuration options will
always overrule options contained in the configuration file.

27. Shell Script 'CompareSp3.sh'
Purpose: Equals configuration file example 'CompareSp3.bnc', compares two SP3
files to calculate RMS values for orbit and clock differences. However, instead
of excluding GPS satellite G05 and GLONASS satellite R18 from the comparison as
specified in 'CompareSp3.bnc', GPS satellite G06 and all GLONASS satellites are
excluded via command line option. BNC runs offline. Comparison results are saved
in a logfile.

Georg Weber, BKG
Frankfurt, April 2016
igs-ip@bkg.bund.de

