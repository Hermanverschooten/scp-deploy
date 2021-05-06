<p align="center">
  <img src="resources/logo.png">
</p>

<p align="center">
  <a href="https://docs.github.com/en/actions/creating-actions/about-actions#types-of-actions"><img alt="Action type" src="https://img.shields.io/badge/Docker%20action-262b31?logo=docker&logoColor=2496ed"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/github/license/marcodallasanta/ssh-scp-deploy"></a>
  <a href="https://github.com/Hermanverschooten/scp-deploy/actions?query=workflow%3ATest"><img alt="Pipeline status" src="https://github.com/Hermanverschooten/scp-deploy/workflows/Test/badge.svg"></a>
</p>

# hv-scp-deploy

## ❔ Why should I use this action?

Because this action provide an easy and higly customizable way to upload files via scp and execute a set of command via ssh before or/and after.  
I use this action to deploy my personal projects to remote server, restarting the needed services or to do a simple upload via scp.

## 🏃 Supported runners
[![Supported runner](https://img.shields.io/badge/Linux-262b31?style=for-the-badge&logo=linux&logoColor=fcc624)](https://docs.github.com/en/actions/creating-actions/about-actions#docker-container-actions)


## 👤 Author

**Herman verschooten**

* Twitter: [@HermvJr](https://twitter.com/HermvJr)
* Github: [@Hermanverschooten](https://github.com/Hermanverschooten)
* LinkedIn: [@Hermanverschooten](https://linkedin.com/in/herman-verschooten-38480220)

This action was forked from Marco Dalla Santa

## ⚙️ Usage
```yaml
    - uses: Hermanverschooten/scp-deploy@{version}
      with:
        local: './'                                                  # Local file path - REQUIRED false - DEFAULT ./
        remote: '~/'                                                 # Remote file path - REQUIRED false - DEFAULT ~/
        host: ${{secrets.HOST}}                                      # Remote server address - REQUIRED true
        port: ${{secrets.PORT}}                                      # Remote server port - REQUIRED false - DEFAULT 22
        user: ${{secrets.USER}}                                      # Remote server user - REQUIRED true
        password: ${{secrets.PASSWORD}}                              # User password - REQUIRED at least one of "password" or "key" 
        key: ${{secrets.KEY}}                                        # Remote server private key - REQUIRED at least one of "password" or "key" 
        pre_upload: echo "This will be executed before the upload!"  # Command to run via ssh before scp upload - REQUIRED false
        post_upload: echo "This will be executed after the upload!"  # Command to run via ssh after scp upload - REQUIRED false
        ssh_options: -o StrictHostKeyChecking=no                     # A set of ssh_option separated by -o - REQUIRED false - DEFAULT -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null
        scp_options: -v                                              # Flags to use during scp - REQUIRED false - DEFAULT ''
```

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

Feel free to check [issues page](https://github.com/Hermanverschooten/scp-deploy/issues).

## 🙏 Thanks

Thanks to [Marco Dalla Santa](https://github.com/marcoallasanta) for the original.

## 📝 License

Copyright © 2021 [Herman verschooten](https://github.com/Hermanverschooten)

Copyright © 2020 [Marco Dalla Santa](https://github.com/marcoallasanta)

The source code, scripts and documentation in this project are released under the [MIT License](LICENSE)
