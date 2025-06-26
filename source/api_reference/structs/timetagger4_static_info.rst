.. c:struct:: timetagger4_static_info

   Structure contains static information

   This structure contains information about the board that does not change
   during run time. It is provided by the function
   :c:func:`timetagger4_get_static_info`.

   .. c:member:: int size

        The number of bytes occupied by the structure.

   .. c:member:: int version

        The version number.

        A version number that is increased when the definition of the
        structure is changed. The increment can be larger than one to match
        driver version numbers or similar. Set to 0 for all versions up to
        first release.

   .. c:member:: int board_id

        ID of the TimeTagger4 board.

        This value is passed to the constructor. It is reflected in the
        output data.

   .. c:member:: int driver_revision

        Encoded version number.

        The lower three bytes contain a triple level hierarchy of
        version numbers. E.g. ``0x010103`` codes version 1.1.3.

        The versioning follows the `Semantic Versioning 2.0.0 <https://semver.org/>`_ 
        specifications.

   .. c:member:: int driver_build_revision

      SVN revision of the driver build.

   .. c:member:: int firmware_revision

      Revision number of the FPGA configuration.

   .. c:member:: int board_revision

      Board revision number.

      The board revision number can be read from a register. It is a
      four bit number that changes when the schematic of the board is
      changed.

      - 0: Experimental first board Version. Labeled "Rev. 1"
      - 2: First commercial Version. Labeled "Rev. 2"

   .. c:member:: int board_configuration

      Describes the schematic configuration of the board.

      The same board schematic can be populated in multiple variants.
      This is a eight bit code that can be read from a register.

   .. c:member:: int subversion_revision

      Subversion revision ID of the FPGA configuration.

   .. c:member:: int chip_id

      16 bit factory ID of the TDC chip.

      This is the chipID as read from the 16 bit THS788 chip ID register
      at SPI address ``0x83``. This value should be cached.

   .. c:member:: int board_serial

      Serial number of the TimeTagger4.

      With year and running number in 8.24 format (8 bits are used to encode the year,
      24 bits are used to encode the serial number).
      The number is identical to the one printed on the silvery sticker on the board.

   .. c:member:: unsigned int flash_serial_low

      Low 32 bits of the 64-bit manufacturer
      serial number of the flash chip.

   .. c:member:: unsigned int flash_serial_high

      High 32 bits of the 64-bit manufacturer
      serial number of the flash chip.

   .. c:member:: crono_bool_t flash_valid

      Flash data is valid and in use.

      If ``true``, the driver found valid calibration data in the flash on
      the board and is using it.

   .. c:member:: char calibration_date

      Calibration date.

      DIN EN ISO 8601 string YYYY-MM-DD HH:DD describing the time when the
      card was calibrated.

   .. c:member:: char bitstream_date

      Bitstream creation date.

      DIN EN ISO 8601 string YYYY-MM-DD HH:DD:SS describing the time when the
      bitstream was created.

   .. c:member:: double delay_bin_size

      Bin size of :c:member:`timetagger4_delay_config.delay` in ps.

   .. c:member:: double auto_trigger_ref_clock

      Auto trigger clock frequency.

      The clock frequency of the auto trigger in Hz
      used for calculating
      :c:member:`timetagger4_configuration.auto_trigger_period`.

   .. c:member:: uint32_t rollover_period

      The number of bins in a rollover period.

      This is a power of 2. The maximum value of a hit's timestamp
      is ``rollover_period - 1``.
