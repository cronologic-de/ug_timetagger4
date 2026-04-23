.. c:struct:: timetagger4_channel

    .. c:member:: crono_bool_t enabled

        Enable the TDC channel.

    .. c:member:: crono_bool_t rising

        Not applicable for the TimeTagger4.

        Rising and/or falling edges are configured using
        :c:struct:`timetagger4_trigger`.

    .. c:member:: uint32_t start

        Start value for the grouping functionality.

        In multiples of :c:member:`timetagger4_param_info.binsize`.

        See also :c:member:`stop` and :ref:`sec grouping`.

        .. attention::

            For continuous mode, :c:member:`timetagger4_channel.start`
            should be kept at its default value
            (as provided by :c:func:`timetagger4_get_default_configuration`).


    .. c:member:: uint32_t stop

        Stop value for the grouping functionality.

        In multiples of :c:member:`timetagger4_param_info.binsize`.

        Only hits between :c:member:`start` and :c:member:`stop` are read out.

        For Gen 1, the range is 0 ≤ :c:member:`start` ≤ :c:member:`stop` ≤ 2\ :sup:`31`.

        For Gen 2, the range is 0 ≤ :c:member:`start` ≤ :c:member:`stop` ≤ 2\ :sup:`32`.

        See also :ref:`sec grouping`.

        .. attention::

            For continuous mode, :c:member:`timetagger4_channel.start`
            should be kept at its default value
            (as provided by :c:func:`timetagger4_get_default_configuration`).
