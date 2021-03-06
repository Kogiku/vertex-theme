themedir       = $(datadir)/themes/Vertex
themedarkdir   = $(datadir)/themes/Vertex-Dark
themelightdir  = $(datadir)/themes/Vertex-Light

ithemedir      = $(DESTDIR)$(themedir)
ithemedarkdir  = $(DESTDIR)$(themedarkdir)
ithemelightdir = $(DESTDIR)$(themelightdir)

install-data-local:
	$(MKDIR_P) $(ithemedir)
	cp $(srcdir)/index.theme $(ithemedir)

if ENABLE_DARK
	$(MKDIR_P) $(ithemedarkdir)
	cp $(srcdir)/index.theme-dark $(ithemedarkdir)/index.theme
endif # ENABLE_DARK


if ENABLE_LIGHT
	$(MKDIR_P) $(ithemelightdir)
	cp $(srcdir)/index.theme-light $(ithemelightdir)/index.theme
endif # ENABLE_LIGHT


if ENABLE_CINNAMON
	cp -R $(srcdir)/cinnamon $(ithemedir)
endif # ENABLE_CINNAMON


if ENABLE_GNOME_SHELL
	$(MKDIR_P) $(ithemedir)/gnome-shell

	$(SASSC) $(srcdir)/gnome-shell/$(GNOME_SHELL_VERSION)/sass/gnome-shell.scss $(srcdir)/gnome-shell/$(GNOME_SHELL_VERSION)/gnome-shell.css;

	cd $(srcdir)/gnome-shell/$(GNOME_SHELL_VERSION) && cp -RL \
		assets \
		gnome-shell.css \
		$(ithemedir)/gnome-shell
endif # ENABLE_GNOME_SHELL


if ENABLE_GTK2
	cp -R $(srcdir)/gtk-2.0 $(ithemedir)
	cd $(ithemedir)/gtk-2.0 && rm -f gtkrc-light

if ENABLE_DARK
	cp -R $(srcdir)/gtk-2.0-dark $(ithemedarkdir)/gtk-2.0
endif # ENABLE_DARK

if ENABLE_LIGHT
	cp -R $(srcdir)/gtk-2.0 $(ithemelightdir)
	cd $(ithemelightdir)/gtk-2.0 && mv gtkrc-light gtkrc
endif # ENABLE_LIGHT
endif # ENABLE_GTK2


if ENABLE_GTK3
	$(SASSC) $(srcdir)/gtk-3.0/$(GTK3_VERSION)/sass/gtk.scss $(srcdir)/gtk-3.0/$(GTK3_VERSION)/gtk.css;
	$(SASSC) $(srcdir)/gtk-3.0/$(GTK3_VERSION)/sass/gtk-light.scss $(srcdir)/gtk-3.0/$(GTK3_VERSION)/gtk-light.css;
	$(SASSC) $(srcdir)/gtk-3.0/$(GTK3_VERSION)/sass/gtk-dark.scss $(srcdir)/gtk-3.0/$(GTK3_VERSION)/gtk-dark.css;

	cp -RH $(srcdir)/gtk-3.0/$(GTK3_VERSION) $(ithemedir)/gtk-3.0

	cd $(ithemedir)/gtk-3.0 && rm -rf \
		gtk-light.css \
		thumbnail-dark.png \
		assets.svg \
		README.md \
		sass \
		*.sh \
		*.txt

if ENABLE_DARK
	cp -RH $(srcdir)/gtk-3.0/$(GTK3_VERSION) $(ithemedarkdir)/gtk-3.0

	cd $(ithemedarkdir)/gtk-3.0 && rm -rf \
		gtk.css \
		gtk-light.css \
		assets.svg \
		README.md \
		sass \
		*.sh \
		*.txt

	cd $(ithemedarkdir)/gtk-3.0 && \
		mv gtk-dark.css gtk.css && \
		mv thumbnail-dark.png thumbnail.png

endif # ENABLE_DARK

if ENABLE_LIGHT
	cp -RH $(srcdir)/gtk-3.0/$(GTK3_VERSION) $(ithemelightdir)/gtk-3.0

	cd $(ithemelightdir)/gtk-3.0 && rm -rf \
		thumbnail-dark.png \
		assets.svg \
		README.md \
		sass \
		*.sh \
		*.txt

	cd $(ithemelightdir)/gtk-3.0 && \
		mv gtk-light.css gtk.css

endif # ENABLE_LIGHT
endif # ENABLE_GTK3



if ENABLE_METACITY
	cp -R $(srcdir)/metacity-1 $(ithemedir)

	cd $(ithemedir)/metacity-1 && rm -f \
		metacity-theme-1-dark.xml \
		metacity-theme-1-light.xml \
		metacity-theme-2-dark.xml \
		metacity-theme-2-light.xml \
		metacity-theme-3-dark.xml \
		metacity-theme-3-light.xml \
		thumbnail-light.png

if ENABLE_DARK
	cp -R $(srcdir)/metacity-1 $(ithemedarkdir)

	cd $(ithemedarkdir)/metacity-1 && rm -f \
		metacity-theme-1.xml \
		metacity-theme-1-light.xml \
		metacity-theme-2.xml \
		metacity-theme-2-light.xml \
		metacity-theme-3.xml \
		metacity-theme-3-light.xml \
		thumbnail-light.png

	cd $(ithemedarkdir)/metacity-1 && \
		mv metacity-theme-1-dark.xml metacity-theme-1.xml && \
		mv metacity-theme-2-dark.xml metacity-theme-2.xml && \
		mv metacity-theme-3-dark.xml metacity-theme-3.xml
endif # ENABLE_DARK

if ENABLE_LIGHT
	cp -R $(srcdir)/metacity-1 $(ithemelightdir)

	cd $(ithemelightdir)/metacity-1 && rm -f \
		metacity-theme-1.xml \
		metacity-theme-1-dark.xml \
		metacity-theme-2.xml \
		metacity-theme-2-dark.xml \
		metacity-theme-3.xml \
		metacity-theme-3-dark.xml

	cd $(ithemelightdir)/metacity-1 && \
		mv metacity-theme-1-light.xml metacity-theme-1.xml && \
		mv metacity-theme-2-light.xml metacity-theme-2.xml && \
		mv metacity-theme-3-light.xml metacity-theme-3.xml && \
		mv thumbnail-light.png thumbnail.png
endif # ENABLE_LIGHT
endif # ENABLE_METACITY


if ENABLE_PLANK

	$(MKDIR_P) $(ithemedir)
	cp -R $(srcdir)/plank $(ithemedir)

if ENABLE_DARK
	$(MKDIR_P) $(ithemedarkdir)
	cp -R $(srcdir)/plank $(ithemedarkdir)
endif # ENABLE_DARKER

if ENABLE_LIGHT
	$(MKDIR_P) $(ithemelightdir)
	cp -R $(srcdir)/plank $(ithemelightdir)
endif # ENABLE_DARK
endif # ENABLE_PLANK


if ENABLE_UNITY
	cp -R $(srcdir)/unity $(ithemedir)

if ENABLE_DARK
	cp -R $(srcdir)/unity $(ithemedarkdir)
endif # ENABLE_DARK

if ENABLE_LIGHT
	cp -R $(srcdir)/unity $(ithemelightdir)
endif # ENABLE_LIGHT
endif # ENABLE_UNITY



if ENABLE_XFWM
	cp -R $(srcdir)/xfwm4 $(ithemedir)

if ENABLE_DARK
	cp -R $(srcdir)/xfwm4 $(ithemedarkdir)
endif # ENABLE_DARK

if ENABLE_LIGHT
	cp -R $(srcdir)/xfwm4-light $(ithemelightdir)/xfwm4
endif # ENABLE_LIGHT
endif # ENABLE_XFWM



uninstall-local:
	rm -rf $(ithemedir)

if ENABLE_DARK
	rm -rf $(ithemedarkdir)
endif # ENABLE_DARK

if ENABLE_LIGHT
	rm -rf $(ithemelightdir)
endif # ENABLE_LIGHT



EXTRA_DIST = \
	cinnamon \
	gnome-shell \
	gtk-2.0 \
	gtk-2.0-dark \
	gtk-3.0 \
	metacity-1 \
	unity \
	plank \
	xfwm4 \
	xfwm4-light \
	index.theme \
	index.theme-light \
	index.theme-dark
