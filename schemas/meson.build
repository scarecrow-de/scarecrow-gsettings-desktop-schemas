schemas = [
  'io.github.scarecrow.desktop.default-applications.gschema.xml',
  'io.github.scarecrow.desktop.interface.gschema.xml',
  'io.github.scarecrow.desktop.lockdown.gschema.xml',
  'io.github.scarecrow.system.locale.gschema.xml',
  'io.github.scarecrow.system.location.gschema.xml',
  'io.github.scarecrow.system.proxy.gschema.xml',
  'io.github.scarecrow.desktop.sound.gschema.xml',
  'io.github.scarecrow.desktop.thumbnail-cache.gschema.xml',
  'io.github.scarecrow.desktop.a11y.gschema.xml',
  'io.github.scarecrow.desktop.a11y.keyboard.gschema.xml',
  'io.github.scarecrow.desktop.a11y.applications.gschema.xml',
  'io.github.scarecrow.desktop.a11y.magnifier.gschema.xml',
  'io.github.scarecrow.desktop.a11y.mouse.gschema.xml',
  'io.github.scarecrow.desktop.thumbnailers.gschema.xml',
  'io.github.scarecrow.desktop.session.gschema.xml',
  'io.github.scarecrow.desktop.background.gschema.xml',
  'io.github.scarecrow.desktop.calendar.gschema.xml',
  'io.github.scarecrow.desktop.datetime.gschema.xml',
  'io.github.scarecrow.desktop.media-handling.gschema.xml',
  'io.github.scarecrow.desktop.screensaver.gschema.xml',
  'io.github.scarecrow.desktop.search-providers.gschema.xml',
  'io.github.scarecrow.desktop.wm.keybindings.gschema.xml',
  'io.github.scarecrow.desktop.wm.preferences.gschema.xml',
  'io.github.scarecrow.desktop.input-sources.gschema.xml',
  'io.github.scarecrow.desktop.privacy.gschema.xml',
  'io.github.scarecrow.desktop.notifications.gschema.xml',
  'io.github.scarecrow.desktop.app-folders.gschema.xml',
  'io.github.scarecrow.desktop.peripherals.gschema.xml',
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
