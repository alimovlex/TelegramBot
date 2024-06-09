# BotPlusPlus
terminate called after throwing an instance of 'boost::wrapexcept<boost::property_tree::ptree_bad_data>'
  what():  conversion of data to type "i" failed
zsh: IOT instruction  ./BotPlusPlus

## To fix this error, make the change here:
```
cmake-build-debug/./_deps/tgbot-src/src/TgTypeParser.cpp
```
## At the following function:
```
User::Ptr TgTypeParser::parseJsonAndGetUser(const ptree& data) const
```
Change 
```
result->id = data.get<int32_t>("id");
```
to
```
result->id = data.get<int64_t>("id");
```
