redis_log_pipe(1) -- a Redis client in Bash
===========================================

<!-- To update README.md: edit man/redis_log_pipe.1.ronn and run `rake man` -->

SYNOPSIS
--------

`redis_log_pipe` <var>key</var> <var>line</var>

DESCRIPTION
-----------

**redis.bash** accepts log lines on STDIN and pipes them to a
[Redis](http://redis.io/) server. Use REDIS_LOG_HOST environment variable to
configure the redis host string.

CAVEATS
-------

 requires a bash with /dev/tcp enabled.

EXIT VALUES
-----------

  * 0: 
    Success

  * 1:
    Redis error

  * 2: 
    Unknown response

COPYRIGHT
------------

redis_log_pipe is Copyright (C) 2011 Rein Henrichs http://reinh.com

- Rein Henrichs: <reinh@reinh.com>

<!-- vim:ft=markdown
-->


[redis_log_pipe(1)]: redis_log_pipe.1.html
