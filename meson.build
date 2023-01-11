project('kerberos-auth', 'c', 'cpp',
    version : '1.0',
    meson_version: '>=0.57.0',
    default_options : [
        'buildtype=debugoptimized',
        'c_std=gnu11',
        'cpp_std=c++20'
    ]
)

# Include directories
incdir = include_directories(
    'src',
)

# Include dependent library
kerberos_dependencies = []
cpp = meson.get_compiler('cpp')
libpam = cpp.find_library('libpam')
kerberos_dependencies += libpam
libc = cpp.find_library('libc')
kerberos_dependencies += libc
a = cpp.find_library('libgssapi_krb5')
kerberos_dependencies += a
b = cpp.find_library('libgssrpc')
kerberos_dependencies += b
c = cpp.find_library('libk5crypto')
kerberos_dependencies += c
d = cpp.find_library('libkadm5clnt_mit')
kerberos_dependencies += d
e = cpp.find_library('libkadm5srv_mit')
kerberos_dependencies += e
f = cpp.find_library('libkdb5')
kerberos_dependencies += f
g = cpp.find_library('libkrad')
kerberos_dependencies += g
h = cpp.find_library('libkrb5')
kerberos_dependencies += h
i = cpp.find_library('libkrb5support')
kerberos_dependencies += i
j = cpp.find_library('libverto')
kerberos_dependencies += j



# Include source file
kerberos_auth_src = files(
    'src/module/account.c',
    'src/module/alt-auth.c',
    'src/module/auth.c',
    'src/module/cache.c',
    'src/module/context.c',
    'src/module/fast.c',
    'src/module/options.c',
    'src/module/password.c',
    'src/module/prompting.c',
    'src/module/public.c',
    'src/module/setcred.c',
    'src/module/support.c',
    'src/pam-util/args.c',
    'src/pam-util/logging.c',
    'src/pam-util/options.c',
    'src/pam-util/vector.c',
    'src/portable/asprintf.c',
    'src/portable/dummy.c',
    'src/portable/issetugid.c',
    'src/portable/krb5-extra.c',
    'src/portable/krb5-profile.c',
    'src/portable/mkstemp.c',
    'src/portable/pam_syslog.c',
    'src/portable/pam_vsyslog.c',
    'src/portable/reallocarray.c',
    'src/portable/strndup.c',
)

# Make dynamic library
shared_library(
    'pam_kerberos_auth',
    kerberos_auth_src ,
    dependencies : kerberos_dependencies,
    include_directories : incdir,
    name_prefix : '',
    install : true
)

