
.. c:struct:: timetagger4_tiger_block

    This struct configures the Timing Generators
    (see also :ref:`sec tiger`).

    .. c:member:: crono_bool_t enable

        Activates the TiGer.

        .. note::

            To use a TiGer, make sure to also set :c:member:`enable_lemo_output` to
            true.

    .. c:member:: crono_bool_t negate

        Inverts the output polarity.

        Default is false.

    .. c:member:: crono_bool_t retrigger

        Enables re-triggering.

        If re-triggering is enabled, the following applies:
        After an event triggered the TiGer output, another event that is detected
        before the :c:member:`stop` value is reached will extend the TiGer output
        for a time :c:member:`stop` minus :c:member:`start`.

    .. c:member:: crono_bool_t extend

        Not applicable for the TimeTagger4.

    .. c:member:: crono_bool_t enable_lemo_output

        Enables the LEMO output.

        Drive the TiGer signal to the corresponding LEMO connector as an output.

        Pulses created by the TiGer are visible at the corresponding input and can
        be used to get their exact timing.

        .. attention::

            The output is DC coupled. Make sure to not connect any devices to
            the corresponding input, as this may damage the device or the TimeTagger4.

    .. c:member:: uint_32_t start

        Configure the duration when the TiGer output is enabled
        relative to the trigger.

        See also :c:member:`stop`.

    .. c:member:: uint_32_t stop

        Configure the duration when the TiGer output is enabled
        relative to the trigger.

        In multiplies of 4 ns for Gen 1 and 3.2 ns for Gen 2.

        The range is 0 :math:`\le` :c:member:`start` :math:`\le` :c:member:`stop`
        :math:`\le` 2\ :sup:`16` – 1.

        After a trigger event, a timer starts. Once the timer reaches
        :c:member:`start`, the TiGer activates. Once the timer reaches
        :c:member:`stop`, the TiGer deactivates.

        If another trigger event is detected before the timer reaches
        :c:member:`stop` and :c:member:`retrigger` is true, the timer resets
        to :c:member:`start`.


    .. c:member:: int sources

        A bitmask with a bit set for all trigger sources that can trigger this
        TiGer block.

        Default is :c:macro:`TIMETAGGER4_TRIGGER_SOURCE_S`.

        Possible trigger sources are

        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_S
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_A
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_B
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_C
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_D
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_S1
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_S2
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_GATE
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_AUTO
        .. c:macro:: TIMETAGGER4_TRIGGER_SOURCE_ONE

        For example, if you want the Start channel and the auto trigger to trigger
        the TiGer block:

        .. code-block:: c

            int bitmask = TIMETAGGER4_TRIGGER_SOURCE_S | TIMETAGGER4_TRIGGER_SOURCE_AUTO;
            config.tiger_block[i].sources = bitmask;


