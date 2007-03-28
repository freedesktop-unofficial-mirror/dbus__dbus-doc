SUBDIRS = tools examples

EXTRA_DIST = \
    config.xsl \
    dbus-introspect-docs.dtd \
    docbook.css

# Creating ChangeLog from git log:

MAINTAINERCLEANFILES = ChangeLog

EXTRA_DIST += ChangeLog

ChangeLog: $(srcdir)/ChangeLog
$(srcdir)/ChangeLog: FORCE
	@if test -d "$(srcdir)/.git"; then \
	  (cd "$(srcdir)" && \
	  ./missing --run git-log --stat) | fmt --split-only > $@.tmp \
	  && mv -f $@.tmp $@ \
	  || ($(RM) $@.tmp; \
	      echo Failed to generate ChangeLog, your ChangeLog may be outdated >&2; \
	      (test -f $@ || echo git-log is required to generate this file >> $@)); \
	else \
	  test -f $@ || \
	  (echo A git checkout and git-log is required to generate ChangeLog >&2 && \
	  echo A git checkout and git-log is required to generate this file >> $@); \
	fi

FORCE:

