using adb

MY_CLAN = "PnG"
MY_VERSION = "1.0"

task :default=>[:docker:build, :controller:spawn, :deploy]

bot_data = {
    bot1: {useraccount: 'username', userpassword: 'password'},
    bot2: {useraccount: 'username2', userpassword: 'password2'}    
}

namespace :controller do
    desc 'Run controller, use port 9000'
    task :build,[:build_num] do |t,args|
        docker run -d -p 9000:9000 \
        -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
    end
end

namespace :docker do
    desc 'Make container'
    task :buildcontainer do |t, args|
        Dir.chdir("aps/bot-docker") do
            @bot_data.each do |b|
                dockerImage == Gem.win_platform? "docker build --privileged -d -p 6080:6080 -p 5554:5554 -p 5555:5555 -e DEVICE='Samsung Galaxy S6' --name android-container butomo1989/docker-android-x86-7.1.1" : "docker run --privileged -d -p 6080:6080 -p 5554:5554 -p 5555:5555 -e DEVICE='Samsung Galaxy S6' --name android-container butomo1989/docker-android-arm-7.1.1"
            end
        end
    end

    desc 'Start container'
    task :startcontainer do |t, args|
        Dir.chdir("apps/bot-docker") do
            @bot_data.each do |b|
                dockerImage == Gem.win_platform? "docker run --privileged -d -p 6080:6080 -p 5554:5554 -p 5555:5555 -e DEVICE='Samsung Galaxy S6' --name android-container butomo1989/docker-android-x86-7.1.1" : "docker run --privileged -d -p 6080:6080 -p 5554:5554 -p 5555:5555 -e DEVICE='Samsung Galaxy S6' --name android-container butomo1989/docker-android-arm-7.1.1"
            end
        end
    end
    desc 'Lets start the bot controlle UIr'
    namespace :controller do
        task :spawn do |t, args|
            docker-compose up -d
        end
    END
end






