qt5_mod = import('qt5')
qt5_dep = dependency('qt5', modules: 'Widgets')

ui_resources = [
   'src/DeviceSelector.ui',
   'src/hid/ControlSubWidget.ui',
   'src/hid/ItemWidget.ui',
   'src/hid/UsageWidget.ui',
   'src/WaitDialog.ui',
   'src/WindowsDriverDialog.ui',
   'src/Window.ui'
]

hidviz_sources = [
   'src/DeviceSelectionListItem.cc',
   'src/DeviceSelector.cc',
   'src/DeviceView.cc',
   'src/FlowLayout.cc',
   'src/hid/CollectionWidget.cc',
   'src/hid/ControlWidget.cc',
   'src/hid/ItemWidget.cc',
   'src/hid/UsageWidget.cc',
   'src/main.cc',
   'src/WaitDialog.cc',
   'src/Window.cc',
   'src/WindowsDriverDialog.cc'
]

moc_headers = [
   'src/DeviceView.hh',
   'src/DeviceSelector.hh',
   'src/hid/ControlWidget.hh',
   'src/hid/UsageWidget.hh',
   'src/Window.hh'
]

qt5_processed = qt5_mod.preprocess(
   moc_headers: moc_headers,  
   ui_files: ui_resources,
   qresources: 'images/images.qrc'
)

hidviz = executable(
   'hidviz',
   sources: [hidviz_sources, qt5_processed],
   include_directories: include_directories('.'),
   dependencies: [
      libhidx_dep,
      libhidx_server_dep,
      qt5_dep,
      buffer_gen_dep,
      protobuf_dep
   ],
   install: (host_machine.system() != 'windows')
)
