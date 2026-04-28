.. raw:: latex

    \clearpage

.. _sec runtime control:

===============
Runtime Control
===============

Once a TimeTagger4 device is configured, the following functions can be used to control
the behavior of it.

These functions return quickly with very little overhead. However, they are not
guaranteed to be thread safe. 


.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{subsection}{timetagger4\_start\_capture}

.. c:function:: int timetagger4_start_capture(timetagger4_device *device)

    Start data acquisition.

    .. note::

        :c:func:`!timetagger4_start_capture` will reset the memory buffer.

        If you wish to stop recording data and resume later without clearing the
        buffer, use :c:func:`timetagger4_pause_capture` and
        :c:func:`timetagger4_continue_capture`.

    :param device: Pointer to a TimeTagger4 device.
    :returns: Status code:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`,
        :c:macro:`TIMETAGGER4_CRONO_INTERNAL_ERROR`,
        :c:macro:`TIMETAGGER4_HARDWARE_FAILURE`, or
        :c:macro:`TIMETAGGER4_WRONG_STATE`.



.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{subsection}{timetagger4\_pause\_capture}

.. c:function:: int timetagger4_pause_capture(timetagger4_device *device)

    Pause data acquisition.

    :c:func:`timetagger4_pause_capture` and :c:func:`timetagger4_continue_capture`
    have less overhead than :c:func:`timetagger4_start_capture` and
    :c:func:`timetagger4_stop_capture`, but do not allow for a
    configuration change.

    :param device: Pointer to a TimeTagger4 device.
    :returns: Status code:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`,
        :c:macro:`TIMETAGGER4_WRONG_STATE`.



.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{subsection}{timetagger4\_continue\_capture}

.. c:function:: int timetagger4_continue_capture(timetagger4_device *device)

    Continue data acquisition.

    :c:func:`timetagger4_pause_capture` and :c:func:`timetagger4_continue_capture`
    have less overhead than :c:func:`timetagger4_start_capture` and
    :c:func:`timetagger4_stop_capture`, but do not allow for a
    configuration change.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`,
        :c:macro:`TIMETAGGER4_WRONG_STATE`.



.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{subsection}{timetagger4\_stop\_capture}

.. c:function:: int timetagger4_stop_capture(timetagger4_device *device)

    Stop data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :returns: Status code:
        :c:macro:`TIMETAGGER4_OK`, or
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`.



.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{subsection}{timetagger4\_start\_tiger}

.. c:function:: int timetagger4_start_tiger(timetagger4_device *device)

    Start the :ref:`Timing Generator (TiGer) <sec tiger>`

    This can be done independently of the state of the data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`, or
        :c:macro:`TIMETAGGER4_WRONG_STATE`.




.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{subsection}{timetagger4\_stop\_tiger}

.. c:function:: int timetagger4_stop_tiger(timetagger4_device *device)

    Stop the :ref:`Timing Generator (TiGer) <sec tiger>`

    This can be done independently of the state of the data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code:
        :c:macro:`TIMETAGGER4_OK` or
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`.