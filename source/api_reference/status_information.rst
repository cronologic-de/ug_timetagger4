.. raw:: latex

    \clearpage

==================
Status Information
==================

timetagger4_get_device_type
===========================

.. c:function:: int timetagger4_get_device_type(timetagger4_device *device)

    Get the type of the TimeTagger device.

    :param device: Pointer to a TimeTagger4 device.
    :return: :c:macro:`CRONO_DEVICE_TIMETAGGER4`

timetagger4_get_last_error_message
==================================

.. c:function:: const char* timetagger4_get_last_error_message(\
    timetagger4_device *device)

    Get the last error message.

    :param device: Pointer to a TimeTagger4 device.
    :return: The error message.

timetagger4_get_fast_info
=========================

.. c:function:: int timetagger4_get_fast_info(\
    timetagger4_device *device,\
    timetagger4_fast_info *info)

    Obtain dynamic information about a TimeTagger4 device that can be obtained
    within a few microseconds.

    :param device: Pointer to a TimeTagger4 device.
    :param info: Pointer to a :c:struct:`timetagger4_fast_info` struct that
        will be filled.
    :return: Status codes:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`,
        :c:macro:`TIMETAGGER4_CRONO_INVALID_ARGUMENTS`, or
        ``-1``.

timetagger4_get_param_info
==========================

.. c:function:: int timetagger4_get_param_info(\
    timetagger4_device *device,\
    timetagger4_fast_info *info)

    Obtain information about configuration changes.

    Gets information that changes indirectly due to configuration changes.

    :param device: Pointer to a TimeTagger4 device.
    :param info: Pointer to a :c:struct:`timetagger4_param_info` struct that
        will be filled.
    :return: Status codes:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_CRONO_INVALID_ARGUMENTS`, or
        :c:macro:`TIMETAGGER4_WRONG_STATE`,


timetagger4_get_static_info
===========================

.. c:function:: int timetagger4_get_static_info(\
    timetagger4_device *device,\
    timetagger4_static_info *info)

    Obtain information about a TimeTagger4 device that does not change during runtime.

    :param device: Pointer to a TimeTagger4 device.
    :param info: Pointer to a :c:struct:`timetagger4_static_info` struct that
        will be filled.
    :return: Status codes:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`, or
        :c:macro:`TIMETAGGER4_CRONO_INVALID_ARGUMENTS`.


timetagger4_get_pcie_info
=========================
    
.. c:function:: int timetagger4_get_pcie_info(\
    timetagger4_device *device,\
    crono_pcie_info *pcie_info)

    Obtain PCIe information.

    :param device: Pointer to a TimeTagger4 device.
    :param pcie_info: Pointer to a :c:struct:`crono_pcie_info` struct that
        will be filled.
    :return: Status codes:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`, or
        :c:macro:`TIMETAGGER4_HARDWARE_FAILURE`.

timetagger4_clear_pcie_errors
=============================

.. c:function:: int timetagger4_clear_pcie_errors(\
    timetagger4_device *device,\
    int flags)

    Clear PCIe errors.

    Only useful for PCIe debugging.

    Valid ``flags`` are:

    .. c:macro:: CRONO_PCIE_CORRECTABLE_FLAG

        Clear correctable PCIe errors.

    .. c:macro:: CRONO_PCIE_UNCORRECTABLE_FLAG

        Clear uncorrectable PCIe errors.

    :param device: Pointer to a TimeTagger4 device.
    :param flag: Flag which errors to clear.
    :return: Status codes:
        :c:macro:`TIMETAGGER4_OK`, or
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`.

timetagger4_fast_info
=====================

.. include:: structs/timetagger4_fast_info.rst

timetagger4_param_info
======================

.. include:: structs/timetagger4_param_info.rst
    
timetagger4_static_info
=======================

.. include:: structs/timetagger4_static_info.rst

crono_pcie_info
===============

.. include:: structs/crono_pcie_info.rst