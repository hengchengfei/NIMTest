source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'
use_frameworks!
inhibit_all_warnings!

def app_pods
    pod 'NIMSDK'               #网易云信
    pod 'SDWebImage', '~> 3.8.2'
    pod 'Toast', '~> 3.0'
    pod 'SVProgressHUD', '~> 2.0.3'
    pod 'M80AttributedLabel', '~> 1.6.3'
    pod 'TZImagePickerController', '~> 1.7.7'
end

target 'aa' do
    app_pods
end

pre_install do |installer|
    def installer.verify_no_static_framework_transitive_dependencies; end
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['ENABLE_BITCODE'] = 'NO'
            config.build_settings['SWIFT_VERSION'] = '3.0' # or '2.3'
        end
    end
end
