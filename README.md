MediaWiki-custom-GlobalUsage-extension
======================================

This is based on https://www.mediawiki.org/wiki/Extension:GlobalUsage

The following changes have been made:

* includes/GlobalUsageImagePageHooks.php
   * function onImagePageAfterImageLinks:
      * import global $wgConf;
      * replace call to WikiMap::getWikiName( $wiki ) by $wgConf->get( 'wgSitename', $wiki );
   * function hasResults:
      * import global $wgDBprefix;
      * concatenate the global to the database name $dbr->getDBname()."-".$wgDBprefix
* includes/SpecialGlobalUsage.php
   * function showResult:
      * import global $wgConf;
      * replace call to WikiMap::getWikiName( $wiki ) by $wgConf->get( 'wgSitename', $wiki );

# Installation
* Extract the extension folder to extensions/GlobalUsage/
* Add the following line to LocalSettings.php:

        wfLoadExtension( 'GlobalUsage' );

* Follow the installation process of the original extension.