.. c:struct:: crono_pcie_info

    .. c:member:: uint32_t pwr_mgmt

        Organizes power supply of the PCIe lanes.

    .. c:member:: uint32_t link_width

        Number of PCIe lanes that the card uses.

    .. c:member:: uint32_t max_payload

        Maximum size in bytes for one PCIe transaction.

    .. c:member:: uint32_t link_speed

        Data rate of the PCIe card.

    .. c:member:: uint32_t error_status_supported

        Different from 0 if the PCIe error status is supported for this device.

    .. c:member:: uint32_t correctable_error_status

        Correctable error status flags.

        Read directly from the PCIe config register.

        Useful for debugging PCIe problems.

        One of the following:

        .. c:macro:: CRONO_PCIE_RX_ERROR
        .. c:macro:: CRONO_PCIE_BAD_TLP
        .. c:macro:: CRONO_PCIE_BAD_DLLP
        .. c:macro:: CRONO_PCIE_REPLAY_NUM_ROLLOVER
        .. c:macro:: CRONO_PCIE_REPLAY_TIMER_TIMEOUT
        .. c:macro:: CRONO_PCIE_ADVISORY_NON_FATAL
        .. c:macro:: CRONO_PCIE_CORRECTED_INTERNAL_ERROR
        .. c:macro:: CRONO_PCIE_HEADER_LOG_OVERFLOW

    .. c:member:: uint32_t uncorrectable_error_status

        Uncorrectable error status flags.

        Read directly from the PCIe config register.

        Useful for debugging PCIe problems.

        One of the following:

        .. c:macro:: CRONO_PCIE_UNC_UNDEFINED
        .. c:macro:: CRONO_PCIE_UNC_DATA_LINK_PROTOCOL_ERROR
        .. c:macro:: CRONO_PCIE_UNC_SURPRISE_DOWN_ERROR
        .. c:macro:: CRONO_PCIE_UNC_POISONED_TLP
        .. c:macro:: CRONO_PCIE_UNC_FLOW_CONTROL_PROTOCOL_ERROR
        .. c:macro:: CRONO_PCIE_UNC_COMPLETION_TIMEOUT
        .. c:macro:: CRONO_PCIE_UNC_COMPLETER_ABORT
        .. c:macro:: CRONO_PCIE_UNC_UNEXPECTED_COMPLETION
        .. c:macro:: CRONO_PCIE_UNC_RECEIVER_OVERFLOW_ERROR
        .. c:macro:: CRONO_PCIE_UNC_MALFORMED_TLP
        .. c:macro:: CRONO_PCIE_UNC_ECRC_ERROR
        .. c:macro:: CRONO_PCIE_UNC_UNSUPPORED_REQUEST_ERROR

