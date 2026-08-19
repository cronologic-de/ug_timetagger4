.. c:struct:: timetagger4_trigger

    Configure if rising or falling or both edges create a trigger event for
    the timing unit or the :ref:`TiGer <sec tiger>`.

    Used for :member:`timetagger4_configuration.trigger`.

    .. c:member:: crono_bool_t falling

        Falling edges will trigger an event.

    .. c:member:: crono_bool_t rising

        Rising edges will trigger an event.
