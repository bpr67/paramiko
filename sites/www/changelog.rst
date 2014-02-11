=========
Changelog
=========

* :bug:`34` (PR :issue:`35`) Fix SFTP prefetching incompatibility with some
  SFTP servers regarding request/response ordering. Thanks to Richard
  Kettlewell for catch & patch.
* :bug:`193` (and its attentant PRs :issue:`230` & :issue:`253`) Fix SSH agent
  problems present on Windows. Thanks to David Hobbs for initial report and to
  Aarni Koskela & Olle Lundberg for the patches.
* :release:`1.10.5 <2014-01-08>`
* :bug:`176` Fix AttributeError bugs in known_hosts file (re)loading. Thanks
  to Nathan Scowcroft for the patch & Martin Blumenstingl for the initial test
  case.
* :release:`1.10.4 <2013-09-27>` 199, 200, 179
* :bug:`179` Fix a missing variable causing errors when an ssh_config file has
  a non-default AddressFamily set. Thanks to Ed Marshall & Tomaz Muraus for
  catch & patch.
* :bug:`200` Fix an exception-causing typo in ``demo_simple.py``. Thanks to Alex
  Buchanan for catch & Dave Foster for patch.
* :bug:`199` Typo fix in the license header cross-project. Thanks to Armin
  Ronacher for catch & patch.
* :release:`1.10.3 <2013-09-20>`
* :bug:`162` Clean up HMAC module import to avoid deadlocks in certain uses of
  SSHClient. Thanks to Gernot Hillier for the catch & suggested fix.
* :bug:`36` Fix the port-forwarding demo to avoid file descriptor errors.
  Thanks to Jonathan Halcrow for catch & patch.
* :bug:`168` Update config handling to properly handle multiple 'localforward'
  and 'remoteforward' keys. Thanks to Emre Yılmaz for the patch.
* :release:`1.10.2 <2013-07-26>`
* :bug:`153` (also :issue:`67`) Warn on parse failure when reading known_hosts
  file.  Thanks to ``@glasserc`` for patch.
* :bug:`146` Indentation fixes for readability. Thanks to Abhinav Upadhyay for
  catch & patch.
* :release:`1.10.1 <2013-04-05>`
* :bug:`142` (`Fabric #811 <https://github.com/fabric/fabric/issues/811>`_)
  SFTP put of empty file will still return the attributes of the put file.
  Thanks to Jason R. Coombs for the patch.
* :bug:`154` (`Fabric #876 <https://github.com/fabric/fabric/issues/876>`_)
  Forwarded SSH agent connections left stale local pipes lying around, which
  could cause local (and sometimes remote or network) resource starvation when
  running many agent-using remote commands. Thanks to Kevin Tegtmeier for catch
  & patch.
* :release:`1.10.0 <2013-03-01>`
* :feature:`66` Batch SFTP writes to help speed up file transfers. Thanks to
  Olle Lundberg for the patch.
* :bug:`133 major` Fix handling of window-change events to be on-spec and not
  attempt to wait for a response from the remote sshd; this fixes problems with
  less common targets such as some Cisco devices. Thanks to Phillip Heller for
  catch & patch.
* :feature:`93` Overhaul SSH config parsing to be in line with ``man
  ssh_config`` (& the behavior of ``ssh`` itself), including addition of parameter
  expansion within config values. Thanks to Olle Lundberg for the patch.
* :feature:`110` Honor SSH config ``AddressFamily`` setting when looking up
  local host's FQDN. Thanks to John Hensley for the patch.
* :feature:`128` Defer FQDN resolution until needed, when parsing SSH config
  files.  Thanks to Parantapa Bhattacharya for catch & patch.
* :bug:`102 major` Forego random padding for packets when running under
  ``*-ctr`` ciphers.  This corrects some slowdowns on platforms where random
  byte generation is inefficient (e.g. Windows). Thanks to  ``@warthog618`` for
  catch & patch, and Michael van der Kolff for code/technique review.
* :feature:`127` Turn ``SFTPFile`` into a context manager. Thanks to Michael
  Williamson for the patch.
* :feature:`116` Limit ``Message.get_bytes`` to an upper bound of 1MB to protect
  against potential DoS vectors. Thanks to ``@mvschaik`` for catch & patch.
* :feature:`115` Add convenience ``get_pty`` kwarg to ``Client.exec_command`` so
  users not manually controlling a channel object can still toggle PTY
  creation. Thanks to Michael van der Kolff for the patch.
* :feature:`71` Add ``SFTPClient.putfo`` and ``.getfo`` methods to allow direct
  uploading/downloading of file-like objects. Thanks to Eric Buehl for the
  patch.
* :feature:`113` Add ``timeout`` parameter to ``SSHClient.exec_command`` for
  easier setting of the command's internal channel object's timeout. Thanks to
  Cernov Vladimir for the patch.
* :support:`94` Remove duplication of SSH port constant. Thanks to Olle
  Lundberg for the catch.
* :feature:`80` Expose the internal "is closed" property of the file transfer
  class ``BufferedFile`` as ``.closed``, better conforming to Python's file
  interface.  Thanks to ``@smunaut`` and James Hiscock for catch & patch.