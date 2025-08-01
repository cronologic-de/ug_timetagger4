.. c:struct:: timetagger4_param_info

    .. c:member:: int size

        The number of bytes this struct occupies.

    .. c:member:: int version

        Version number of this struct. It is increased when the definition of the
        struct changes.

    .. c:member:: double binsize

        Bin size in ps of the measured TDC data.

        | For Gen 1 boards, this is 500 ps.
        | For Gen 2 boards, this is 100 ps.

    .. c:member:: int board_id

        ID of the TimeTagger4 device.

        Used to identify itself in the output data stream.

        Is between 0 and 255.

    .. c:member:: int channels

        Number of TDC channels of the board.

        Fixed at 4.

    .. c:member:: int channel_mask

        Bit assignment of each enabled input channel.

        Bit 0 ≤ *n* ≤ 3 is set if channel *n* is enabled.

    .. c:member:: int64_t total_buffer

        The total amount of DMA buffer in bytes.

    .. c:member:: double packet_binsize

        The binsize used for the TimeTagger4.

        The TDC data timestamps of :c:member:`crono_packet.data` is given in
        multiples of this value.

        | For Gen 1 boards, this is 500 ps.
        | For Gen 2 boards, this is 100 ps.

    .. c:member:: double quantisation

        Quantisation, that is, measurement resolution of the TimeTagger4, in ps.

        Depends on the board variant:

        +--------+--------+---------+--------+-------+--------+
        | –1G    | –2G    | –1.25G  | –2.5G  | –5G   | –10G   |
        +--------+--------+---------+--------+-------+--------+
        | 1000   | 500    | 800     | 400    | 200   | 100    |
        +--------+--------+---------+--------+-------+--------+

        That means that, e.g., for the –1.25G, the lower 3 bits of the timestamps of
        :c:member:`crono_packet.data` are 0.

