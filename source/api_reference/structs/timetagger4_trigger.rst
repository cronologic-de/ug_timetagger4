.. c:struct:: timetagger4_trigger

    Configure if rising or falling or both edges create a trigger event for
    :c:struct:`timetagger4_tiger_block`.

    .. c:member:: crono_bool_t falling

        Falling edges will trigger an event.

    .. c:member:: crono_bool_t rising

        Rising edges will trigger an event.
