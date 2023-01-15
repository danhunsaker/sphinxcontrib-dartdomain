Simple Test
###########

.. dart:package:: package_info_plus

.. dart:class:: PackageInfo

   Application metadata. Provides application bundle information on iOS and
   application package information on Android.

   .. dart:method:: fromPlatform()

      :return: Future\<:dart:class:`PackageInfo`>

      Retrieves package information from the platform. The result is cached.

   .. dart:attribute:: appName

      The app name. ``CFBundleDisplayName`` on iOS, ``application/label`` on
      Android.

   .. dart:attribute:: buildNumber

      The build number. ``CFBundleVersion`` on iOS, ``versionCode`` on Android.

   .. dart:attribute:: buildSignature

      The build signature. Empty string on iOS, signing key signature (hex) on
      Android.

   .. dart:attribute:: installerStore

      The installer store. Indicates through which store this application was
      installed.

   .. dart:attribute:: packageName

      The package name. ``bundleIdentifier`` on iOS, ``getPackageName`` on
      Android.

   .. dart:attribute:: version

      The package version. ``CFBundleShortVersionString`` on iOS,
      ``versionName`` on Android.
