schemas = [
  'io.github.scarecrow_de.desktop.default-applications.gschema.xml',
  'io.github.scarecrow_de.desktop.interface.gschema.xml',
  'io.github.scarecrow_de.desktop.lockdown.gschema.xml',
  'io.github.scarecrow_de.system.locale.gschema.xml',
  'io.github.scarecrow_de.system.location.gschema.xml',
  'io.github.scarecrow_de.system.proxy.gschema.xml',
  'io.github.scarecrow_de.desktop.sound.gschema.xml',
  'io.github.scarecrow_de.desktop.thumbnail-cache.gschema.xml',
  'io.github.scarecrow_de.desktop.a11y.gschema.xml',
  'io.github.scarecrow_de.desktop.a11y.keyboard.gschema.xml',
  'io.github.scarecrow_de.desktop.a11y.applications.gschema.xml',
  'io.github.scarecrow_de.desktop.a11y.magnifier.gschema.xml',
  'io.github.scarecrow_de.desktop.a11y.mouse.gschema.xml',
  'io.github.scarecrow_de.desktop.thumbnailers.gschema.xml',
  'io.github.scarecrow_de.desktop.session.gschema.xml',
  'io.github.scarecrow_de.desktop.background.gschema.xml',
  'io.github.scarecrow_de.desktop.calendar.gschema.xml',
  'io.github.scarecrow_de.desktop.datetime.gschema.xml',
  'io.github.scarecrow_de.desktop.media-handling.gschema.xml',
  'io.github.scarecrow_de.desktop.screensaver.gschema.xml',
  'io.github.scarecrow_de.desktop.search-providers.gschema.xml',
  'io.github.scarecrow_de.desktop.wm.keybindings.gschema.xml',
  'io.github.scarecrow_de.desktop.wm.preferences.gschema.xml',
  'io.github.scarecrow_de.desktop.input-sources.gschema.xml',
  'io.github.scarecrow_de.desktop.privacy.gschema.xml',
  'io.github.scarecrow_de.desktop.notifications.gschema.xml',
  'io.github.scarecrow_de.desktop.app-folders.gschema.xml',
  'io.github.scarecrow_de.desktop.peripherals.gschema.xml',
]

conf = configuration_data()
conf.set('prefix', prefix)
conf.set('exec_prefix', prefix)
conf.set('libdir', libdir)
conf.set('bindir', bindir)
conf.set('libexecdir', libexecdir)
conf.set('datarootdir', datadir)
conf.set('datadir', datadir)
conf.set('includedir', includedir)

generated_schemas = []
foreach schema: schemas
  generated_schemas += configure_file(
    output: schema,
    input: schema + '.in',
    configuration: conf,
  )
endforeach

install_data(generated_schemas, install_dir: schemasdir)

install_data(
  'scarecrow-gsettings-desktop-schemas.convert',
  'scarecrow-wm-schemas.convert',
  install_dir: join_paths(datadir, 'GConf', 'gsettings'),
)
