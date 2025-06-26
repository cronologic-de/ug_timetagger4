.. c:struct:: timetagger4_delay_config

    Only available for TimeTagger4 Gen 2.

    .. c:member:: uint32_t delay

        Delay the corresponding input channel.

        In units of :c:member:`timetagger4_static_info.delay_bin_size`.

        The range is 0 :math:`\le` :c:member:`delay` :math:`\le` 1023.

        See also :ref:`sec input delay`.

