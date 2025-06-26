.. c:struct:: timetagger4_configuration

    This struct is used to configure a TimeTagger4 device using
    :c:func:`timetagger4_configure`.

    .. c:member:: int size

        The number of bytes this struct occupies.

    .. c:member:: int version

        Version number of this struct. It is increased when the definition of the
        struct changes.

    .. c:member:: int tdc_mode

        Operational mode of the TDC.

        Must be one of the following:

        .. c:macro:: TIMETAGGER4_TDC_MODE_GROUPED

            Operate in grouped mode.

            Classical Common-Start operation. See also :ref:`sec grouping`.

        .. c:macro:: TIMETAGGER4_TDC_MODE_CONTINUOUS

            Operate in continuous mode.

            See also :ref:`sec continuous mode`.

            :c:member:`auto_trigger_period` must be set appropriately.

            :c:member:`channel[i].stop <channel>` must be larger than
            :c:member:`auto_trigger_period`. TODO improve documentation

    .. c:member:: crono_bool_t start_rising

        Not applicable for the TimeTagger4. Rising and/or falling edges are configured
        using :c:struct:`timetagger4_trigger`.

    .. c:member:: double dc_offset[TIMETAGGER4_TDC_CHANNEL_COUNT + 1]

        Set the threshold voltage for the input channels S, A–D.

        See also :numref:`fig-input-circuit`.

        - ``dc_offset[0]``: Threshold for channel Start.
        - ``dc_offset[1-4]``: Thresholds for Stop channels A–D.

        The supported range is –1.27 to 1.13 V.

        The threshold should be close to 50% of the height of the input pulse.

        The effective resolution is about :math:`\pm` 4 mV.

        .. note::

            The inputs are AC coupled. Thus, the absolute voltage is not important for
            pulse inputs. It is the relative pulse amplitude that causes the input
            circuit to switch. The parameter must be set to the relative switching
            voltage for the input standard in use.

            If the pulses are negative, a negative switching threshold must be set
            and vice versa.

        .. attention::

            The supported range changed for :ref:`driver release<sec driver revisions>`
            1.10.7. That means, if you use a value for ``dc_offset`` outside the new
            supported range in your source code, the device configuration will
            adjust it automatically to the new supported range (e.g., a value of
            1.18 V will be reduced to 1.13 V).

        Values for various signaling standards are provided as macros:

        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_NIM
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_CMOS
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_LVCMOS_33
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_LVCMOS_25
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_LVCMOS_18
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_TTL
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_LVTTL_33
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_LVTTL_25
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_SSTL_3
        .. c:macro:: TIMETAGGER4_DC_OFFSET_P_SSTL_2
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_NIM
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_CMOS
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_LVCMOS_33
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_LVCMOS_25
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_LVCMOS_18
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_TTL
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_LVTTL_33
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_LVTTL_25
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_SSTL_3
        .. c:macro:: TIMETAGGER4_DC_OFFSET_N_SSTL_2

    .. c:member:: timetagger4_trigger trigger[TIMETAGGER4_TRIGGER_COUNT]

        Configuration of the polarity of the external trigger sources.

        External trigger sources are used as inputs for the TiGer blocks and as
        inputs to the time measurement unit.

        Index 0 refers to the Start channel, indices 1
        through 4 to the Stop channels A through D.

    .. c:member:: timetagger4_tiger_block tiger_block[TIMETAGGER4_TIGER_COUNT]

        Configuration of the :ref:`Timing Generators <sec tiger>`.

        Index 0 refers to the TiGer connected to the Start channel, indices 1
        through 4 to the TiGer-Units connected to the Stop channels A through D.

    .. c:member:: timetagger4_channel channel[TIMETAGGER4_TDC_CHANNEL_COUNT]

        Configuration of the Stop channels.

        Indices 0 through 3 refer to the Stop channels A through D.

    .. c:member:: timetagger4_lowres_channel \
        lowres_channel[TIMETAGGER4_LOWRES_CHANNEL_COUNT]

        Not applicable for the TimeTagger4.

        This field is part of the struct to ensure driver compatibility with other
        cronologic boards.

    .. c:member:: uint32_t auto_trigger_period

        Configure the base frequency of the
        :ref:`auto trigger function generator <sec auto trigger>`.

        See also :c:member:`auto_trigger_random_exponent`.

    .. c:member:: uint32_t auto_trigger_random_exponent

        Configure the randomness of the 
        :ref:`auto trigger function generator <sec auto trigger>`.

        There is no enable or reset of the auto trigger.

        Given the two parameters :c:member:`auto_trigger_period` (*M*) and
        :c:member:`auto_trigger_random_exponent` (*N*), the frequency *T* of the
        auto trigger function generator will be

        .. math::

            T = M + [1 \dots 2^N] - 1

        Depending on :c:member:`tdc_mode`, the following restrictions apply

        :c:macro:`TIMETAGGER4_TDC_MODE_GROUPED <tdc_mode.TIMETAGGER4_TDC_MODE_GROUPED>`
            *M*\ :sub:`min` :math:`\le` *M* < 2\ :sup:`32` and 0 :math:`\le` *N* < 32
            
            *M*\ :sub:`min` is 6 for Gen 1 and 8 for Gen 2.

        :c:macro:`TIMETAGGER4_TDC_MODE_CONTINUOUS <tdc_mode.TIMETAGGER4_TDC_MODE_CONTINUOUS>`
            31 :math:`\le` *M* < 78125000 and 0 :math:`\le` *N* < 32

        .. note::

            The auto trigger can be used as a source of the TiGer blocks
            (:c:member:`timetagger4_tiger_block.source`).


    .. c:member:: timetagger4_delay_config delay_config[TIMETAGGER4_TDC_CHANNEL_COUNT + 1]

        Configuration of the channel delays.

        Index 0 refers to the Start channel, indices 1
        through 4 to the Stop channels A through D.

    .. c:member:: uint32_t ignore_empty_packets

        If enabled (any value but 0), do not write empty packets to the output stream.

        Disabled by default.
