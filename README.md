# wellkens2025
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
