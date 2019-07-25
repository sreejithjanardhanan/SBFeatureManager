# SBFeatureManager

This is an implementation of a feature manager provides provision to add/remove features in iOS application based on requirement for iOS written in Swift 4.0.

# Requirements

* iOS 8.0+
* XCode 9.0+
* Swift 4.2

# Usage

1. Modify FeatureMetaData.plist by adding all features in application. 

2. Provide featureID, featureName, featureRequiredUseCases, featureControllerName, featureStoryboardSource,    featureControllerIdentifier.

3. In App delegate, register all application feature.

        // Applications Features will be registered when they are implemented one by one
        SBFeatureManager.sharedManager.registerFeature(KEYCONSTANTS.Feature.kFirstFeatureKey)
        SBFeatureManager.sharedManager.registerFeature(KEYCONSTANTS.Feature.kSecondFeatureKey)
        SBFeatureManager.sharedManager.registerFeature(KEYCONSTANTS.Feature.kThirdFeatureKey)
        
        
4. Activate features.

        // ONLY FIRST FEATURE
        // let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kFirstFeature)])
        
        // ONLY SECOND FEATURE
        // let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kSecondFeature)])
        
        // ONLY THIRD FEATURE
        // let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kThirdFeature)])
        
        // FIRST AND SECOND FEATURE
        // let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kFirstFeature) , NSNumber.init(value: INT.FeatureUseCase.kSecondFeature)])
        
        // SECOND AND THIRD FEATURE
        // let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kSecondFeature) , NSNumber.init(value: INT.FeatureUseCase.kThirdFeature)])
        
        // FIRST AND THIRD FEATURE
        // let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kFirstFeature) , NSNumber.init(value: INT.FeatureUseCase.kThirdFeature)])
        
        // FIRST, SECOND AND THIRD FEATURE
          let useCaseSet = Set([NSNumber.init(value: INT.FeatureUseCase.kFirstFeature) , NSNumber.init(value: INT.FeatureUseCase.kSecondFeature), NSNumber.init(value: INT.FeatureUseCase.kThirdFeature)])
        
        SBFeatureManager.sharedManager.activateFeaturesOnUseCases(useCaseSet)



