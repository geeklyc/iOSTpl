# Uncomment the next line to define a global platform for your project
platform :ios, '8.0'
inhibit_all_warnings!

source 'git@github.com:geeklyc/BC_Specs.git'
source 'https://github.com/CocoaPods/Specs.git'

use_frameworks!

target 'iOSTpl' do
  # Pods for iOSTpl
   # v1.7.0增加特性
 supports_swift_versions '<= 4.2'

 # 响应式编程
 pod 'RxSwift', '~> 4.5.0'
 pod 'RxCocoa', '~> 4.5.0'
 # 布局
 pod 'SnapKit', '~> 4.2.0'
 # 网络请求
 pod 'Moya', '~> 12.0.1'
 # 模型解析
 pod 'ObjectMapper', '~> 3.4.2'
 # 键盘管理
 pod 'IQKeyboardManagerSwift', '~> 6.4.0'
 # 代码规范
 pod 'SwiftLint', '~> 0.33.1'
 script_phase :name => 'SwiftLintScript', :script => '"${PODS_ROOT}/SwiftLint/swiftlint"'

 pod 'BC_Mediator'

  target 'iOSTplTests' do
    inherit! :search_paths
    # Pods for testing

    #pod 'Quick', '2.0.0'
    #pod 'Nimble', '8.0.0'

  end

end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['GCC_ENABLE_OBJC_GC'] = 'supported'
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '8.0'
      config.build_settings['SWIFT_VERSION'] = '4.2'
      config.build_settings['GCC_OPTIMIZATION_LEVEL'] = 's'  #更快更小
      if config.name == "Debug" then
        config.build_settings['COPY_PHASE_STRIP'] = 'NO'
        config.build_settings['SWIFT_OPTIMIZATION_LEVEL'] = '-O'  #速度优化
        elsif config.name == "Release" then
        config.build_settings['COPY_PHASE_STRIP'] = 'YES'
        config.build_settings['SWIFT_OPTIMIZATION_LEVEL'] = '-Osize'  #大小优化
      end
    end
  end
end