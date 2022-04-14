# -*- mode: ruby -*-
# vi: set ft=ruby :

# This file was generated by SecGen
# 2022-04-14 08:48:59 +0800
# Based on scenarios/default_scenario.xml

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "escalation" do |escalation|

    escalation.vm.provider :virtualbox do |vb|
      vb.gui = false
      vb.customize ['modifyvm', :id, '--pae', 'on']
      vb.customize ['modifyvm', :id, '--hwvirtex', 'on']
      vb.customize ['modifyvm', :id, '--vtxvpid', 'off']
      vb.memory = '1024'
    end

    
    escalation.vm.boot_timeout = 600
    escalation.ssh.connect_timeout = 600

    # SecGen datastore
    # {}

    # SecGen modules

    # base: modules/bases/debian_stretch_server
    #   id: scenariosystembase
    #   attributes: {"module_path"=>["modules/bases/debian_stretch_server"], "name"=>["Debian 9 Stretch Server"], "author"=>["Thomas Shaw"], "module_license"=>["GPLv3"], "description"=>["Debian 9.5.0 Stretch Server amd64. For testing purposes, the default root password is puppet."], "cpu_word_size"=>["64-bit"], "type"=>["server", "cli"], "platform"=>["linux", "unix"], "distro"=>["Debian 9.5.0 Stretch amd64"], "url"=>["https://app.vagrantup.com/secgen/boxes/debian_stretch_server/versions/1.3/providers/virtualbox.box"], "esxi_url"=>["https://app.vagrantup.com/redwiz666/boxes/debian_stretch_server/versions/1.0.0/providers/vmware.box"], "ovirt_template"=>["stretch_desktop_kde_20210911"], "software_license"=>["various"], "conflict"=>["\n    bases/.*\n  "]}
    #   conflicts: [{"module_path"=>["bases/.*"]}]
    #   requires: []
    
    escalation.vm.box = "modules_bases_debian_stretch_server"
    escalation.vm.box_url = "https://app.vagrantup.com/secgen/boxes/debian_stretch_server/versions/1.3/providers/virtualbox.box"
    
    

    # utility: modules/utilities/unix/update/unix_update
    #   id: 
    #   attributes: {"module_path"=>["modules/utilities/unix/update/unix_update"], "name"=>["Unix update repository"], "author"=>["Jason Keighley"], "module_license"=>["Apache v2"], "description"=>["An update module for unix"], "type"=>["update"], "platform"=>["linux"]}
    #   conflicts: []
    #   requires: []
    escalation.vm.provision "puppet" do | modules_utilities_unix_update_unix_update |
      modules_utilities_unix_update_unix_update.module_path = "puppet/escalation/modules"
      
        modules_utilities_unix_update_unix_update.environment_path = "environments/"
        modules_utilities_unix_update_unix_update.environment_variables = {'RUBYOPT' => '-W0'}
        modules_utilities_unix_update_unix_update.environment = "production"
      
      modules_utilities_unix_update_unix_update.synced_folder_type = "rsync"
      modules_utilities_unix_update_unix_update.manifests_path = "puppet/escalation/modules/unix_update"
      modules_utilities_unix_update_unix_update.manifest_file = "unix_update.pp"
    end

    # generator: modules/generators/messages/welcome_message
    #   id: scenariosystemvulnerability11generator2modulesvulnerabilitiesunixmiscdistccexec
    #   attributes: {"module_path"=>["modules/generators/messages/welcome_message"], "name"=>["Welcome Message Generator"], "author"=>["Thomas Shaw"], "module_license"=>["MIT"], "description"=>["Generates a welcome message."], "type"=>["string_generator", "message_generator", "local_calculation"], "platform"=>["linux", "windows"], "output_type"=>["generated_strings"]}
    #   conflicts: []
    #   requires: []
    #   writes out ('["G'day mate!"]') to scenariosystemvulnerability1 -> strings_to_leak

    # generator: modules/generators/messages/random_ascii_art
    #   id: scenariosystemvulnerability11generator1modulesvulnerabilitiesunixmiscdistccexec
    #   attributes: {"module_path"=>["modules/generators/messages/random_ascii_art"], "name"=>["Random ASCII Art Generator"], "author"=>["Z. Cliffe Schreuders"], "module_license"=>["MIT"], "description"=>["Selects and outputs random ascii art image from the lib/resources/ascii_art/computers directory."], "type"=>["message_generator", "ascii_art_generator", "local_calculation"], "platform"=>["linux", "windows"], "output_type"=>["ascii_art"]}
    #   conflicts: []
    #   requires: []
    #   writes out ('["  ,=====================.\n  |                     |\n  |.-------------------.|\n  ||[ _ o     . .  _ ]_||\n  |`-------------------'|\n  ||                   ||\n  |`-------------------'|\n  ||                   ||\n  |`-------------------'|\n  ||                   ||\n  |`-----------------_-'|\n  ||[=========]| o  (@) |\n  |`---------=='/u\\ --- |\n  |------_--------------|\n  | (/) (_)           []|\n  |---==--==----------==|\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||dxm|||\n  |||||||||||||||||||||||\n  |=====================|\n .'                     `.\n\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\n"]') to scenariosystemvulnerability1 -> strings_to_leak

    # generator: modules/generators/filenames/random_filename
    #   id: scenariosystemvulnerability12generator2modulesvulnerabilitiesunixmiscdistccexec
    #   attributes: {"module_path"=>["modules/generators/filenames/random_filename"], "name"=>["Random Filename Generator"], "author"=>["Thomas Shaw"], "module_license"=>["MIT"], "description"=>["Random filename generator using the Faker ruby gem."], "type"=>["string_generator", "filename_generator", "filename", "local_calculation"], "platform"=>["linux", "windows"], "reference"=>["https://github.com/stympy/faker"], "read_fact"=>["file_name", "extension"], "output_type"=>["filename"]}
    #   conflicts: []
    #   requires: []
    #   writes out ('["velit.json"]') to scenariosystemvulnerability1 -> leaked_filenames

    # generator: modules/generators/filenames/random_filename
    #   id: scenariosystemvulnerability12generator1modulesvulnerabilitiesunixmiscdistccexec
    #   attributes: {"module_path"=>["modules/generators/filenames/random_filename"], "name"=>["Random Filename Generator"], "author"=>["Thomas Shaw"], "module_license"=>["MIT"], "description"=>["Random filename generator using the Faker ruby gem."], "type"=>["string_generator", "filename_generator", "filename", "local_calculation"], "platform"=>["linux", "windows"], "reference"=>["https://github.com/stympy/faker"], "read_fact"=>["file_name", "extension"], "output_type"=>["filename"]}
    #   conflicts: []
    #   requires: []
    #   writes out ('["illum.jpeg"]') to scenariosystemvulnerability1 -> leaked_filenames

    # vulnerability: modules/vulnerabilities/unix/misc/distcc_exec
    #   id: scenariosystemvulnerability1
    #   attributes: {"module_path"=>["modules/vulnerabilities/unix/misc/distcc_exec"], "name"=>["DistCC Daemon Command Execution"], "author"=>["Lewis Ardern"], "module_license"=>["MIT"], "description"=>["Distcc has a documented security weakness that enables remote code execution."], "type"=>["distcc"], "privilege"=>["user_rwx"], "access"=>["remote"], "platform"=>["unix"], "difficulty"=>["medium"], "read_fact"=>["strings_to_leak", "leaked_filenames"], "default_input"=>["\n    \n    \n  ", "\n    \n    \n  "], "cve"=>["CVE-2004-2687"], "cvss_base_score"=>["9.3"], "cvss_vector"=>["AV:N/AC:M/Au:N/C:C/I:C/A:C"], "reference"=>["https://www.rapid7.com/db/modules/exploit/unix/misc/distcc_exec", "OSVDB-13378"], "software_name"=>["distcc"], "software_license"=>["GPLv2"], "msf_module"=>["exploit/unix/misc/distcc_exec"], "hint"=>["On a non-standard port"], "solution"=>["Distcc is vulnerable, and on a high port number."], "conflict"=>["\n    distcc\n  "], "requires"=>["\n    update\n  "], "CyBOK"=>["\n    EXPLOITATION\n    EXPLOITATION FRAMEWORKS\n  ", "\n    CVEs and CWEs\n  ", "\n    PENETRATION TESTING - SOFTWARE TOOLS\n    PENETRATION TESTING - ACTIVE PENETRATION\n  "]}
    #   conflicts: [{"software_name"=>["distcc"]}]
    #   requires: [{"type"=>["update"]}]
    #   received_inputs: {"strings_to_leak"=>["G'day mate!", "  ,=====================.\n  |                     |\n  |.-------------------.|\n  ||[ _ o     . .  _ ]_||\n  |`-------------------'|\n  ||                   ||\n  |`-------------------'|\n  ||                   ||\n  |`-------------------'|\n  ||                   ||\n  |`-----------------_-'|\n  ||[=========]| o  (@) |\n  |`---------=='/u\\ --- |\n  |------_--------------|\n  | (/) (_)           []|\n  |---==--==----------==|\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||||||||\n  |||||||||||||||||dxm|||\n  |||||||||||||||||||||||\n  |=====================|\n .'                     `.\n\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\"\n"], "leaked_filenames"=>["velit.json", "illum.jpeg"]}
    escalation.vm.provision "puppet" do | modules_vulnerabilities_unix_misc_distcc_exec |
      modules_vulnerabilities_unix_misc_distcc_exec.facter = {
        "base64_inputs_file" => 'distcc_exec_ed2ad973c2a7f4de72635076e5c0bc',
      }
      modules_vulnerabilities_unix_misc_distcc_exec.module_path = "puppet/escalation/modules"
      
        modules_vulnerabilities_unix_misc_distcc_exec.environment_path = "environments/"
        modules_vulnerabilities_unix_misc_distcc_exec.environment_variables = {'RUBYOPT' => '-W0'}
        modules_vulnerabilities_unix_misc_distcc_exec.environment = "production"
      
      modules_vulnerabilities_unix_misc_distcc_exec.synced_folder_type = "rsync"
      modules_vulnerabilities_unix_misc_distcc_exec.manifests_path = "puppet/escalation/modules/distcc_exec"
      modules_vulnerabilities_unix_misc_distcc_exec.manifest_file = "distcc_exec.pp"
    end

    # vulnerability: modules/vulnerabilities/unix/access_control_misconfigurations/suid_root_less
    #   id: scenariosystemvulnerability2
    #   attributes: {"module_path"=>["modules/vulnerabilities/unix/access_control_misconfigurations/suid_root_less"], "name"=>["Access control mis-configurations suid less root"], "author"=>["Jason Keighley"], "module_license"=>["Apache v2"], "description"=>["Mis-configure files to enable root privileges"], "type"=>["access_control_misconfiguration", "suid_root_viewer_shell"], "privilege"=>["root_rwx"], "access"=>["local"], "platform"=>["unix"], "hint"=>["Text viewer permission misconfiguration"], "solution"=>["Less editor running as user root"], "CyBOK"=>["\n    access control\n    Elevated privileges\n    Vulnerabilities and attacks on access control misconfigurations\n  ", "\n    Access controls and operating systems\n    Linux security model\n    Attacks against SUID\n  "]}
    #   conflicts: []
    #   requires: []
    escalation.vm.provision "puppet" do | modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less |
      modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.module_path = "puppet/escalation/modules"
      
        modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.environment_path = "environments/"
        modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.environment_variables = {'RUBYOPT' => '-W0'}
        modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.environment = "production"
      
      modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.synced_folder_type = "rsync"
      modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.manifests_path = "puppet/escalation/modules/suid_root_less"
      modules_vulnerabilities_unix_access_control_misconfigurations_suid_root_less.manifest_file = "suid_root_less.pp"
    end

    # service: modules/services/unix/http/apache_stretch_compatible/apache
    #   id: 
    #   attributes: {"module_path"=>["modules/services/unix/http/apache_stretch_compatible/apache"], "name"=>["Apache HTTP Server - Stretch/Kali Compatible"], "author"=>["Z. Cliffe Schreuders", "Connor Wilson", "Puppet Labs"], "module_license"=>["Apache v2"], "description"=>["An installation of Apache"], "type"=>["httpd"], "platform"=>["linux"], "reference"=>["https://httpd.apache.org/", "https://forge.puppet.com/puppetlabs/apache"], "software_name"=>["apache"], "software_license"=>["Apache v2"], "conflict"=>["\n    apache\n  ", "\n    .*Wheezy.*\n  "], "requires"=>["\n    update\n  "]}
    #   conflicts: [{"software_name"=>["apache"]}, {"name"=>[".*Wheezy.*"]}]
    #   requires: [{"type"=>["update"]}]
    #   received_inputs: {""=>[]}
    escalation.vm.provision "puppet" do | modules_services_unix_http_apache_stretch_compatible_apache |
      modules_services_unix_http_apache_stretch_compatible_apache.facter = {
        "base64_inputs_file" => 'apache_87f5aeaea7fc35089eef01fe552b63',
      }
      modules_services_unix_http_apache_stretch_compatible_apache.module_path = "puppet/escalation/modules"
      
        modules_services_unix_http_apache_stretch_compatible_apache.environment_path = "environments/"
        modules_services_unix_http_apache_stretch_compatible_apache.environment_variables = {'RUBYOPT' => '-W0'}
        modules_services_unix_http_apache_stretch_compatible_apache.environment = "production"
      
      modules_services_unix_http_apache_stretch_compatible_apache.synced_folder_type = "rsync"
      modules_services_unix_http_apache_stretch_compatible_apache.manifests_path = "puppet/escalation/modules/apache"
      modules_services_unix_http_apache_stretch_compatible_apache.manifest_file = "apache.pp"
    end

    # service: modules/services/unix/http/apache_bash_cgi
    #   id: scenariosystemservice
    #   attributes: {"module_path"=>["modules/services/unix/http/apache_bash_cgi"], "name"=>["Apache Bash CGI"], "author"=>["Thomas Shaw"], "module_license"=>["MIT"], "description"=>["Hosts a bash CGI script on a default apache installation."], "type"=>["http_bash"], "platform"=>["unix"], "reference"=>["https://httpd.apache.org/"], "software_license"=>["Apache v2"], "conflict"=>["\n    webapp\n  "], "requires"=>["\n    .*apache\n    httpd\n  "]}
    #   conflicts: [{"type"=>["webapp"]}]
    #   requires: [{"module_path"=>[".*apache"], "type"=>["httpd"]}]
    escalation.vm.provision "puppet" do | modules_services_unix_http_apache_bash_cgi |
      modules_services_unix_http_apache_bash_cgi.module_path = "puppet/escalation/modules"
      
        modules_services_unix_http_apache_bash_cgi.environment_path = "environments/"
        modules_services_unix_http_apache_bash_cgi.environment_variables = {'RUBYOPT' => '-W0'}
        modules_services_unix_http_apache_bash_cgi.environment = "production"
      
      modules_services_unix_http_apache_bash_cgi.synced_folder_type = "rsync"
      modules_services_unix_http_apache_bash_cgi.manifests_path = "puppet/escalation/modules/apache_bash_cgi"
      modules_services_unix_http_apache_bash_cgi.manifest_file = "apache_bash_cgi.pp"
    end

    # network: modules/networks/host_only/private_network_3
    #   id: scenariosystemnetwork
    #   attributes: {"module_path"=>["modules/networks/host_only/private_network_3"], "name"=>["Private Network #3"], "author"=>["Z. Cliffe Schreuders"], "module_license"=>["GPLv3"], "description"=>["A network using DHCP"], "type"=>["private_network"], "range"=>["dhcp"]}
    #   conflicts: []
    #   requires: []

    escalation.vm.network :private_network, type: "dhcp", auto_config: false

            # ip_address_for_escalation=DHCP

  end

end
