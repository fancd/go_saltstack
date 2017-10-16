# go_saltstack

简单使用
	P := &CONFIG{}
	P.Salt_host = ""
	P.Salt_user = ""
	P.Salt_passwd = ""

	err:=P.GET_TOKEN()
	if err != nil{
		log.Println(err)
	}else {
		post_data := fmt.Sprintf(`{"fun": "%s", "client": "%s", "tgt": "%s"}`, "grains.items", "local", "*")
		info,err := P.CMD_SALT(post_data)
		if err !=nil{
			log.Println(err)
		}else {
			fmt.Println(info)
		}
	}
