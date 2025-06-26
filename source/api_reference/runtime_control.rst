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

timetagger4_start_capture
=========================

.. c:function:: int timetagger4_start_capture(timetagger4_device *device)

    Start data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code: TODO


timetagger4_pause_capture
=========================

.. c:function:: int timetagger4_pause_capture(timetagger4_device *device)

    Pause data acquisition.

    :c:func:`timetagger4_pause_capture` and :c:func:`timetagger4_continue_capture`
    have less overhead than :c:func:`timetagger4_start_capture` and
    :c:func:`timetagger4_stop_capture`, but do not allow for a
    configuration change.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code: TODO


timetagger4_continue_capture
============================

.. c:function:: int timetagger4_continue_capture(timetagger4_device *device)

    Continue data acquisition.

    :c:func:`timetagger4_pause_capture` and :c:func:`timetagger4_continue_capture`
    have less overhead than :c:func:`timetagger4_start_capture` and
    :c:func:`timetagger4_stop_capture`, but do not allow for a
    configuration change.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code: TODO


timetagger4_stop_capture
=========================

.. c:function:: int timetagger4_stop_capture(timetagger4_device *device)

    Stop data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code: TODO


timetagger4_start_tiger
=======================

.. c:function:: int timetagger4_start_tiger(timetagger4_device *device)

    Start the :ref:`Timing Generator (TiGer) <sec tiger>`

    This can be done independently of the state of the data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code: TODO


timetagger4_stop_tiger
=======================

.. c:function:: int timetagger4_stop_tiger(timetagger4_device *device)

    Stop the :ref:`Timing Generator (TiGer) <sec tiger>`

    This can be done independently of the state of the data acquisition.

    :param device: Pointer to a TimeTagger4 device.
    :return: Status code: TODO