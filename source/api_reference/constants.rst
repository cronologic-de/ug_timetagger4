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

.. c:macro:: TIMETAGGER4_LOWRES_CHANNEL_COUNT

    There are no additional channels for the TimeTagger4.

    This macro is included for driver compatibility with other cronologic boards.

.. c:type:: crono_bool_t

    Data type used for booleans in various structs.

Status Codes
============

.. c:macro:: TIMETAGGER4_OK

    Return value of various API functions if no error occurred.

.. c:macro:: TIMETAGGER4_INVALID_DEVICE

.. c:macro:: CRONO_INVALID_ARGUMENTS

cronologic Device IDs
=====================

.. c:macro:: CRONO_DEVICE_UNKNOWN

.. c:macro:: CRONO_DEVICE_HPTDC

.. c:macro:: CRONO_DEVICE_NDIGO5G

.. c:macro:: CRONO_DEVICE_NDIGO250M

.. c:macro:: CRONO_DEVICE_NDIGO_AVRG

.. c:macro:: CRONO_DEVICE_XTDC4

.. c:macro:: CRONO_DEVICE_FMC_TDC10

.. c:macro:: CRONO_DEVICE_TIMETAGGER4

.. c:macro:: CRONO_DEVICE_D_AVE12

.. c:macro:: CRONO_DEVICE_D_AVE14

.. c:macro:: CRONO_DEVICE_NDIGO2G14

.. c:macro:: CRONO_DEVICE_XHPTDC8

.. c:macro:: CRONO_DEVICE_NDIGO6G12