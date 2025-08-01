.. raw:: latex

    \clearpage

===================
Constants and Types
===================

General
=======

.. c:macro:: TIMETAGGER4_TDC_CHANNEL_COUNT
    
    The number of TDC input channels.

.. c:macro:: TIMETAGGER4_TIGER_COUNT

   The number of :ref:`timing generators <sec tiger>`.

.. c:macro:: TIMETAGGER4_TRIGGER_COUNT

    The number of potential trigger sources for the
    :ref:`timing generators <sec tiger>`.

    One for each TDC input and one for the Start input, as well as some special
    trigger. See :c:member:`timetagger4_tiger_block.sources` for more information.

.. c:macro:: TIMETAGGER4_API_VERSION
    
    Current version of the API.

.. c:type:: crono_bool_t

    Data type used for booleans in various structs.

Status Codes
============

.. c:macro:: TIMETAGGER4_OK

    ``0``. Return value of various API functions if no error occurred.

.. c:macro:: TIMETAGGER4_WRONG_STATE

    ``4``. The TimeTagger4 is in the wrong state for the requested action (e.g.,
    continuing to capture when the capture was not paused).

.. c:macro:: TIMETAGGER4_INVALID_DEVICE

    ``5``. The device pointer passed to various API functions was invalid.

.. c:macro:: TIMETAGGER4_INVALID_BUFFER_PARAMETERS

    ``8``. Invalid buffer parameters were used when configuring a TimeTagger4 device.

.. c:macro:: TIMETAGGER4_INVALID_CONFIG_PARAMETERS

    ``9``. The parameters used for configuring a TimeTagger4 device were invalid.

.. c:macro:: TIMETAGGER4_HARDWARE_FAILURE

    ``11``. A hardware failure occurred.

.. c:macro:: TIMETAGGER4_DEVICE_OPEN_FAILED

    ``14``. Failed to open the TimeTagger4 device during initialization.

.. c:macro:: TIMETAGGER4_CRONO_INTERNAL_ERROR
    
    ``15``. An internal error occurred.

.. c:macro:: TIMETAGGER4_CRONO_INVALID_ARGUMENTS

    ``17``. The arguments passed to various API functions were invalid.

cronologic Device IDs
=====================

.. c:macro:: CRONO_DEVICE_TIMETAGGER4