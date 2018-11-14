# pikachubot <codes python>

Codes:
ban: 
if message.content.startswith("!ban"):
        if not message.author.server_permissions.ban_members:
            return await client.send_message(message.channel, "**Você não tem permissão para executar esse comando bobinho(a)!**")
        try:
            user = message.mentions[0]
            await client.send_message(message.channel, "**O usuario(a) <@{}> foi banido com sucesso do servidor.**".format(user.id))
            await client.ban(user,delete_message_days=1)
        except IndexError:
            await client.send_message(message.channel, "**Você deve especificar um usuario para banir!**")
        except discord.Forbidden:
            await client.send_message(message.channel, "**Não posso banir o usuário, o cargo dele está acima de mim ou não tenho permissão para banir membros**!")
        finally:
            pass
  
