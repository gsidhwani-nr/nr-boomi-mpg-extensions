# nr-boomi-mpg-extensions
# 1.4 Interim Draft
Handled Security issues and added Executors Instrumentation and removed the Queue Instrumenation as it was removing the Web Trsansaction as it seems to become 
the parent Transaction.

##Step to Deploy.

###replace all extensions from R1.4 to extensions directory of newrelic. https://github.com/gsidhwani-nr/nr-boomi-mpg-extensions/archive/refs/tags/r1.4.zip 
      Please double check all items are placed as in r1.4 and there are no extra files.
###revert procworker.sh to procworker.sh with security settings on. Please double check
     i.e. Add Back "-Djava.security.policy==${BOOMI_ATOM_HOME}/bin/procworker-${ATOM_SECURITY_LEVEL}.policy" "-Djava.security.manager=com.boomi.security.ExtendedSecurityManager"
###save it and restart.

###The low level services transaction we will tune iteratively in coming week(s).
