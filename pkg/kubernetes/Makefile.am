
kubernetesdir = $(pkgdatadir)/kubernetes
kubernetes_DATA = \
	pkg/kubernetes/app.min.css.gz \
	pkg/kubernetes/cluster.min.html.gz \
	pkg/kubernetes/kubernetes.min.js.gz \
	pkg/kubernetes/manifest.json \
	pkg/kubernetes/tool.min.html.gz \
	$(NULL)

kubernetesdebugdir = $(DBGDIR)$(kubernetesdir)
kubernetesdebug_DATA = \
	pkg/kubernetes/angular.js \
	pkg/kubernetes/app.css \
	pkg/kubernetes/app.js \
	pkg/kubernetes/client.js \
	pkg/kubernetes/cluster.html \
	pkg/kubernetes/dashboard.js \
	pkg/kubernetes/kubernetes.js \
	pkg/kubernetes/tool.html \
	$(NULL)

kubernetes_BUNDLE = \
	pkg/kubernetes/angular.min.js \
	pkg/kubernetes/app.min.js \
	pkg/kubernetes/client.min.js \
	pkg/kubernetes/dashboard.min.js \
	$(NULL)

pkg/kubernetes/kubernetes.min.js: $(kubernetes_BUNDLE)
	$(AM_V_GEN) $(srcdir)/tools/missing $(srcdir)/tools/jsbundle $@ $^

kubernetes_TESTS = \
	pkg/kubernetes/test-kubernetes.html \
	$(NULL)

TESTS += $(kubernetes_TESTS)

CLEANFILES += \
	pkg/kubernetes/app.min.css \
	pkg/kubernetes/cluster.min.html \
	pkg/kubernetes/kubernetes.min.js \
	pkg/kubernetes/tool.min.html \
	$(kubernetes_BUNDLE) \
	$(NULL)

EXTRA_DIST += \
	pkg/kubernetes/cluster.min.html \
	pkg/kubernetes/kubernetes.min.js \
	pkg/kubernetes/tool.min.html \
	$(kubernetes_BUNDLE) \
	$(kubernetes_DATA) \
	$(kubernetesdebug_DATA) \
	$(kubernetes_TESTS) \
	pkg/kubernetes/mock-basic.js \
	pkg/kubernetes/mock-large.js \
	pkg/kubernetes/angular.min.js \
	pkg/kubernetes/angular-config.js \
	$(NULL)

update-lib::
	$(srcdir)/tools/jsbundle $(srcdir)/pkg/kubernetes/angular.js \
	    $(srcdir)/lib/angular.$(VX).js \
	    $(srcdir)/lib/angular-route.$(VX).js \
	    $(srcdir)/pkg/kubernetes/angular-config.js
	$(srcdir)/tools/jsbundle $(srcdir)/pkg/kubernetes/angular.min.js \
	    $(srcdir)/lib/angular.$(VX).min.js \
	    $(srcdir)/lib/angular-route.$(VX).min.js \
	    $(srcdir)/pkg/kubernetes/angular-config.js

# Never recreate these files
pkg/kubernetes/angular.min.js:
	@true
