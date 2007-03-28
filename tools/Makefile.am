doctoolsdir = $(bindir)

doctools_SCRIPTS = \
    spec-strip-docs \
    spec-to-docbook

docxsldir = $(datadir)/dbus-doc/xsl

docxsl_DATA = \
    spec-strip-docs.xsl \
    spec-to-docbook.xsl

do_subst = sed -e 's,[@xsldir[@],$(xsldir),g'

spec-strip-docs: spec-strip-docs.in
	$(do_subst) <  $(srcdir)/spec-strip-docs.in > spec-strip-docs

spec-to-docbook: spec-to-docbook.in
	$(do_subst) <  $(srcdir)/spec-to-docbook.in > spec-to-docbook
