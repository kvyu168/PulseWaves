****************************************************************

  pulse2pulse

  reads full waveform LIDAR data from a variety of proprietary
  formats and stores it to the PulseWaves format. Also computes
  an intensity value from the waves file that is stored in the
  pulse file and that can be used for easier understanding and
  navigation in pulseview
 
  For updates you can follow PulseWaves at

  http://rapidlasso.com/PulseWaves
  http://pulsewaves.org
  http://github.com/PulseWaves
  http://twitter.com/LaserPulseWaves
  http://facebook.com/LaserPulseWaves

  Martin @LaserPulseWaves

****************************************************************

example use:

>> pulse2pulse.exe -version
>> pulse2pulse.exe -i lidar.pls -gui
>> pulse2pulse.exe -i lidar.plz -start_at_pulse 10000 -o lidar.pls 
>> pulse2pulse.exe -i lidar.laz -subseq 0 10000 -o lidar.pls 
>> pulse2pulse.exe -i lidar.laz -subseq 0 10000 -o lidar.pls -owvz
>> pulse2pulse.exe -i lidar.lgc -subseq 0 10000 -o lidar.pls -keep_descriptor 0
>> pulse2pulse.exe -i lidar.lgw -subseq 0 10000 -o lidar.pls -drop_first_x_above 630500
>> pulse2pulse.exe -i lidar.pls -o lidar_intensity.pls -compute_intensity

for more info:

D:\PulseTools\bin>pulse2pulse.exe -h
Filter pulses based on their first waveform sample.
  -keep_first 630000 4834000 631000 4836000 (min_x min_y max_x max_y)
  -drop_first_x_below 630000.50 (min_x)
  -drop_first_y_below 4834500.25 (min_y)
  -drop_first_x_above 630500.50 (max_x)
  -drop_first_y_above 4836000.75 (max_y)
  -keep_first_z 11.125 130.725 (min_z, max_z)
  -drop_first_z_below 11.125 (min_z)
  -drop_first_z_above 130.725 (max_z)
Filter pulses based on their last waveform sample.
  -keep_last 630000 4834000 631000 4836000 (min_x min_y max_x max_y)
  -drop_last_x_below 630000.50 (min_x)
  -drop_last_y_below 4834500.25 (min_y)
  -drop_last_x_above 630500.50 (max_x)
  -drop_last_y_above 4836000.75 (max_y)
  -keep_last_z 11.125 130.725 (min_z, max_z)
  -drop_last_z_below 11.125 (min_z)
  -drop_last_z_above 130.725 (max_z)
Filter pulses based on anchor point.
  -keep_anchor 630000 4834000 631000 4836000 (min_x min_y max_x max_y)
  -drop_anchor_x_below 630000.50 (min_x)
  -drop_anchor_y_below 4834500.25 (min_y)
  -drop_anchor_x_above 630500.50 (max_x)
  -drop_anchor_y_above 4836000.75 (max_y)
  -keep_anchor_z 11.125 130.725 (min_z, max_z)
  -drop_anchor_z_below 11.125 (min_z)
  -drop_anchor_z_above 130.725 (max_z)
Filter pulses based on the internally stored integer time stamp.
  -keep_T 401003726000 401003728000
  -drop_T_below 401003726000
  -drop_T_above 401003728000
  -drop_T_between 401003726000 401003728000
Filter pulses based on a double-precision float GPS time stamp.
  -keep_time 401003.726 401003.728
  -drop_time_below 401003.726
  -drop_time_above 401003.728
  -drop_time_between 401003.726 401003.728
Filter pulses based on their pulse descriptor.
  -keep_descriptor 1 2
  -drop_descriptor 0
Filter pulses based on scan direction or mirror facet.
  -scan_direction_change_only
  -edge_of_scan_line_only
  -keep_scan_direction 1
  -drop_scan_direction 0
  -keep_facet 1 3
  -drop_facet 0
Filter pulses with simple thinning.
  -keep_every_nth 2
  -keep_random_fraction 0.1
Transform coordinates.
  -translate_x -2.5
  -translate_z 42.1
  -translate_xyz 0.5 0.5 0.01
  -switch_x_y
  -switch_y_z
  -switch_x_z
Transform raw XYZ integers.
  -translate_Z 20
  -translate_XYZ 2 2 0
Transform intensity.
  -scale_intensity 2.5
  -translate_intensity 50
  -translate_then_scale_intensity 0.5 3.1
Modify the classification.
  -set_classification 2
  -change_classification_from_to 2 4
Modify the pulse source ID.
  -set_pulse_source_ID 500
  -change_pulse_source_ID_from_to 1023 1024
Transform the time stamps.
  -translate_T 40500000
  -translate_time 40.50
Transform flags and else.
  -set_mirror_facet 0
  -change_mirror_facet_from_to 1 2
Supported Pulse Inputs
  -i lidar.pls
  -i lidar.plz
  -i lidar.lgw
  -i lidar.lgc
  -i lidar13fwf.las
  -i lidar13fwf.laz
  -h
Supported Pulse Outputs
  -o pulse.pls
  -o pulse.pls -owvz
  -o human_readable.txt
PulseTools (by martin@rapidlasso.com) version 0.3 rev 11 (150617)
usage:
pulse2pulse -i las13fwf.las -o out.pls
pulse2pulse -i in.pls -o out.pls -compute_intensity
pulse2pulse -i lvis.lgw -o lvis.pls
pulse2pulse -i geolas.lgc -o geolas.pls
pulse2pulse -i riegl.plz -o riegl.pls
pulse2pulse -h

---------------

if you find bugs let me (martin.isenburg@rapidlasso.com) know.
