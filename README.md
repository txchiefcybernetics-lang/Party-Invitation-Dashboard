# wellkens2025 | Protocol error (Storage.getUsageAndQuota): Quota information is not available
```
Channel: DevTools
Initial URL: https://kenwellitsolution.com/api/path/finder
Chrome Version: 153.0.0.0
Stack Trace: Error: Protocol error (Storage.getUsageAndQuota): Quota information is not available
    at LighthouseError.fromProtocolMessage (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:1065:436)
    at devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2246:207
    at async getImportantStorageWarning (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2254:1186)
    at async resetStorageForUrl (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2259:119)
    at async prepareTargetForNavigationMode (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2260:192)
    at async _setup (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2264:1240)
    at async gatherFn (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2267:439)
    at async Runner.gather (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2235:423)
    at async navigationGather (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2267:546)
    at async navigation (devtools://devtools/bundled/third_party/lighthouse/lighthouse-dt-bundle.js:2267:1528)
```
  class AssetLoggerPlugin {
  apply(compiler) {
    compiler.hooks.thisCompilation.tap("AssetLoggerPlugin", (compilation) => {
      const logger = compilation.getLogger("AssetLoggerPlugin");
      compilation.hooks.processAssets.tap(
        {
          name: "AssetLoggerPlugin",
          stage: compilation.constructor.PROCESS_ASSETS_STAGE_SUMMARIZE,
        },
        (assets) => {
          logger.info("Generated assets:");
          for (const assetName of Object.keys(assets)) {
            logger.info(assetName);
          }
        },
      );
    });
  }
}

export default AssetLoggerPlugin;
