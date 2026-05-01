schemas = [
  'io.github.scarecrow-de.desktop.default-applications.gschema.xml',
  'io.github.scarecrow-de.desktop.interface.gschema.xml',
  'io.github.scarecrow-de.desktop.lockdown.gschema.xml',
  'io.github.scarecrow-de.system.locale.gschema.xml',
  'io.github.scarecrow-de.system.location.gschema.xml',
  'io.github.scarecrow-de.system.proxy.gschema.xml',
  'io.github.scarecrow-de.desktop.sound.gschema.xml',
  'io.github.scarecrow-de.desktop.thumbnail-cache.gschema.xml',
  'io.github.scarecrow-de.desktop.a11y.gschema.xml',
  'io.github.scarecrow-de.desktop.a11y.keyboard.gschema.xml',
  'io.github.scarecrow-de.desktop.a11y.applications.gschema.xml',
  'io.github.scarecrow-de.desktop.a11y.magnifier.gschema.xml',
  'io.github.scarecrow-de.desktop.a11y.mouse.gschema.xml',
  'io.github.scarecrow-de.desktop.thumbnailers.gschema.xml',
  'io.github.scarecrow-de.desktop.session.gschema.xml',
  'io.github.scarecrow-de.desktop.background.gschema.xml',
  'io.github.scarecrow-de.desktop.calendar.gschema.xml',
  'io.github.scarecrow-de.desktop.datetime.gschema.xml',
  'io.github.scarecrow-de.desktop.media-handling.gschema.xml',
  'io.github.scarecrow-de.desktop.screensaver.gschema.xml',
  'io.github.scarecrow-de.desktop.search-providers.gschema.xml',
  'io.github.scarecrow-de.desktop.wm.keybindings.gschema.xml',
  'io.github.scarecrow-de.desktop.wm.preferences.gschema.xml',
  'io.github.scarecrow-de.desktop.input-sources.gschema.xml',
  'io.github.scarecrow-de.desktop.privacy.gschema.xml',
  'io.github.scarecrow-de.desktop.notifications.gschema.xml',
  'io.github.scarecrow-de.desktop.app-folders.gschema.xml',
  'io.github.scarecrow-de.desktop.peripherals.gschema.xml',
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
  'gsettings-desktop-schemas.convert',
  'wm-schemas.convert',
  install_dir: join_paths(datadir, 'GConf', 'gsettings'),
)
