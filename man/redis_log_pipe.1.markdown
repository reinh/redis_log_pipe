redis_log_pipe(1) -- Pipe log lines from STDIN to redis
========================================================

<!-- To update README.md: edit man/redis_log_pipe.1.ronn and run `rake man` -->

DESCRIPTION
-----------

redis_log_pipe takes log lines on STDIN and pipes them to [redis](http://redis.io). 

It connects to a redis server located at <var>REDIS_LOG_HOST</var> (default: 127.0.0.1:6379). 

It [LPUSHes](http://redis.io/commands/lpush) them to a
[LIST](http://redis.io/topics/data-types) called "<var>key</var>".  It trims the list to
<var>RETENTION</var> (default: 250) using [LTRIM](http://redis.io/commands/ltrim).  It
also [PUBLISHes](http://redis.io/commands/publish) them to a
[channel](http://redis.io/topics/pubsub) called "channels.<var>key</var>".

ARGUMENTS
---------

  * key:
    The redis key to use for the list.

    By convention, the log will be published to a channel named channels.<var>key</var> as well.

ENVIRONMENT VARIABLES
---------------------

  * REDIS_LOG_HOST:
    [<var>password</var>@]<var>host</var>:<var>port</var>  

    The redis password, host and port. Password optional.  
    Default: 127.0.0.1:6379

  * RETENTION:
    Number of log lines to retain in the list for tailing.  
    Default: 250

CAVEATS
-------

 * requires a bash with /dev/tcp enabled.

COPYRIGHT
------------

redis_log_pipe is Copyright (C) 2011 Rein Henrichs http://reinh.com

- Rein Henrichs: <reinh@reinh.com>

<!-- vim:ft=markdown
-->


[redis_log_pipe(1)]: redis_log_pipe.1.html
