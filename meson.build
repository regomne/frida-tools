project('frida-tools', 'c', version: '1.0.0')

python = get_option('python')
if python == ''
  python = find_program('python3', required: false)
  if not python.found()
    python = find_program('python')
  endif
endif

result = run_command(python, '-c',
  'import sys; sys.stdout.write("%d.%d" % (sys.version_info[0], sys.version_info[1]))',
  check: true)
python_version = result.stdout()

python_name = 'python' + python_version
python_site_packages = get_option('libdir') / python_name / 'site-packages'

pkgdir = python_site_packages / 'frida_tools'

subdir('agents')
subdir('frida_tools')
subdir('scripts')
