if not get_option('local_install')
  chatprefix = chat_dep.get_pkgconfig_variable('prefix')

  install_data('io.github.zoitechat.Plugin.OTR.metainfo.xml',
    install_dir: join_paths(chatprefix, get_option('datadir'), 'metainfo')
  )
endif

appstream_util = find_program('appstream-util', required: false)
if appstream_util.found()
  test('Validate appstream file', appstream_util,
    args: ['validate', files('io.github.zoitechat.Plugin.OTR.metainfo.xml')]
  )
endif
