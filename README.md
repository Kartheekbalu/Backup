<!--   SITES
          Enable different web sites for different domains in the same Sitecore structure
          Supported attributes:

              mode: [on|off]. If set to 'off', the site will be disabled. Default value: 'on'.

              name: Name of the site.

              hostName: The host name of the incoming url. May include wildcards (ex. www.site.net, *.site.net, *.net, pda.*, print.*.net)
                        It's possible to set more than one mask by using '|' symbol as a separator (ex. pda.*|print.*.net)

              targetHostName: The host name to use when generating URLs to items within this site from the context of another site.
                              If the targetHostName attribute is absent, Sitecore uses the value of the hostName attribute instead.
                              Used only when the value of the Rendering.SiteResolving setting is true.

              port: The port number of the incoming url. Default value: 80
              
              externalPort: The port number that is used to generate links that can access the site from outside the network when the site is behind NAT.

              virtualFolder: The prefix to match for incoming URL's.
                             This value will be removed from the URL and the remainder will be treated as the item path.

              physicalFolder: The physical location of files for the site.
                              If the site is based on physical files, this is the path to the folder holding the files.
                              For non-physical sites, this is the place where Sitecore looks for a default.aspx file (to start the pipelines).

              rootPath: The path to the root item of the site.
                        The item path specified in the URL will be appended to this value to find the item.

              startItem: The path to the start item of the site.
                         This is used as the default item path if no path is specified in the URL.
                         It will be combined with rootPath to find the default item of the site.

              language: Default language for the site.

              database: Database containing items to be used for rendering the site.
              content: Database containing items to be edited.
              contentLanguage: The default editing language in the client.
              contentStartItem: The path to the start item when using the client.

              masterDatabase: The database containing the data to be shown in preview and web edit modes.

              device: The name of the device to use for the site. If not specified, the device resolver will find a 'best match device'.

              filterItems: If true, the site will always show the current version of an item (without publishing)
              filteredItemsCacheSize: The size of the cache used to store filtered items. Specify the value in bytes or append the value with KB, MB or GB

              cacheHtml: If true, HTML caching will be enabled. If false, no HTML will be cached for any rendering. Default value: false.
              htmlCacheSize: The size of the html cache. Specify the value in bytes or append the value with KB, MB or GB

              cacheMedia: If true, media caching will be enabled. If false, no media will be cached. Default value: true.
              mediaCachePath: The path to the folder where media data will be cached. Default value: {temp folder}/{site name}/mediacache.

              cacheRenderingParameters: Specifies whether the RenderingItem Parameters cache should be enabled.
                                       If false, caching is disabled and the value of the Parameters property of the RenderingItem object is recalculated every time it is accessed.
                                       To improve the performance of page rendering on content delivery servers, you should enable caching of the Parameters value.
                                       We recommend that you disable RenderingItem Parameters caching on content management servers.
                                       Default value: false
              renderingParametersCacheSize: The size of the RenderingItem Parameters cache. Specify the value in bytes or append the value with KB, MB or GB.

              domain: The security domain of the site.
              requireLogin: If true, login will be required to enter the site.
              loginPage: The path to the login page to use. Must point to a physical file or a page in a site that does NOT require login.

              enableDebugger: Indicates if the debugger is enabled on the site. Typically this is only the website.
              enablePreview: Indicates if preview is enabled on the site. Typically this is only the website.
              enableWebEdit: Indicates if WebEdit is enabled on the site. Typically this is only the website.
              enableWorkflow: Must be true to enable workflows for the site.
              enableTracking: Determines whether website tracking is enabled or not. Default value: true.
              explicitConsentForTrackingIsRequired: Determines whether explicit consent for tracking is required. 
                                      Default value: false.
              isInternal: Indicates if a site is used for internal purposes. Default value: false.

              enforceVersionPresence: If set to true, '404 Not Found' error page will be shown if a context item does not have a requested version.
                                      Default value: false.

              allowDebug: Must be true to be able to debug the site.

              browserTitle: The title of the browser window when browsing the site.

              disableBrowserCaching: If set to true, browser caching is disabled for the site. If set to false, browser caching is enabled for the site. If absent,
                                     the value of the DisableBrowserCaching setting in the <settings> section determines browser caching for the site.

              disableClientData: If set to true, the use of ClientDataStore will be disabled for the site.

              disableXmlControls: If set to true, loading Xml Controls as pages will be disabled.

              defaultDevice: The device to use if no specific device matches the request. This setting takes precedence over the default
              device as it is set by Default checkbox for Device item.
              
              dictionaryDomain: The default domain to use when looking up dictionary phrases for the website. If a phrase does not exist in
                                this dictionary domain, Sitecore attempts to locate that phrase in the default dictionary domain - 
                                /sitecore/system/Dictionary in the current database. If the phrase cannot be found in the default dictionary
                                domain, Sitecore attempts to locate that phrase in the default dictionary domain in the Core database, if that
                                database exists.
                                You can override the site-specific dictionary domain by passing parameters to the Translate.Text() method.

              inherits: Indicates that the attributes should be inherited from another site. To enable inheritance, you must specify the name of the source site.
                        Attributes that are explicitly specified overwrite the attributes that are inherited from the source site.
                        
              analyticsDefinitions: The database where the Analytics definition items for this site are stored. To use the content database for the site, specify "content". 
                                    If this attribute is not specified, the current context database is used. If the context database is not set, for example, for code 
                                    that runs in a background job, the value of the DefaultDefinitionDatabase setting in the Sitecore.Analytics.config file is used. 
              previewUnpublishableItems: Allows users to preview items that cannot be published yet. Default value: false.
              disableTrailingWildcard: Disables the use of trailing wildcards when resolving the name of a website.
                                       For example, when set to true, 'test.com' is not be matched to '*test.c'. Default value: false.
              errorPageUrl: The URL to redirect to, if a generic error occurs.
                            Default value: if not specified, the value of the ErrorPage setting in the <settings> section is used.
              noAccessUrl: The URL to redirect to, if access to an item is denied.
                           Default value: if not specified, the value of the NoAccessUrl setting in the <settings> section is used.
              noLicenseUrl: The URL to redirect to, if a license is missing.
                            Default value: if not specified, the value of the NoLicenseUrl setting in the <settings> section is used.
              layoutNotFoundUrl: The URL to redirect to, if an items layout is not found.
                                 Default value: if not specified, the value of the LayoutNotFoundUrl setting in the <settings> section is used.
              itemNotFoundUrl: The URL to redirect to, if an item is not found.
                               Default value: if not specified, the value of the ItemNotFoundUrl setting in the <settings> section is used.
              linkItemNotFoundUrl: The URL to redirect to, if an item being linked to is not found.
                                   Default value: if not specified, the value of the LinkItemNotFoundUrl setting in the <settings> section is used.
              noPublishableUrl: The URL of the page that handles errors if no publishable item or version of an item can be found.
                                Default value: if not specified, the value of the NoPublishableUrl setting in the <settings> section is used.
              mediaLinkServerUrl: The URL to use when Sitecore generates media links and when Media.AlwaysIncludeServerUrl is set to true. This is typically
                                  used when all media is served from one or more dedicated instances or when your solution is configured to store Sitecore media on
                                  a content delivery network. The URL must use this format: <protocol>://<hostname>, for example http://example.com 
                                  If not set a vlue from Media.MediaLinkServerUrl is used. If Media.MediaLinkServerUrl is empty as well URL of the current site is used. Default value empty.
           List of all default sites can be found in ./App_Config/Sitecore/CMS.Core/Sitecore.Sites.config.
         -->
