.. c:struct:: timetagger4_channel

    .. c:member:: crono_bool_t enabled

        Enable the TDC channel.

    .. c:member:: crono_bool_t rising

        Not applicable for the TimeTagger4.

        Rising and/or falling edges are configured using
        :c:struct:`timetagger4_trigger`.

    .. c:member:: uint32_t start

        Start value for the grouping functionality.

        See also :c:member:`stop` and :ref:`sec grouping`.

        In multiples of :c:member:`timetagger4_param_info.binsize`.

    .. c:member:: uint32_t stop

        Stop value for the grouping functionality.

        See also :ref:`sec grouping`.

        In multiples of :c:member:`timetagger4_param_info.binsize`.

        Only hits between :c:member:`start` and :c:member:`stop` are read out.

        The range is 0 :math:`\le` :c:member:`start` :math:`\le` :c:member:`stop`
        :math:`\le` 2\ :sup:`31`.
