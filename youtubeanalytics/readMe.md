# Youtube Analytics

This is a fork of the youtubeanalytics/v2 golang library than can be found here:
https://github.com/googleapis/google-api-go-client/blob/master/youtubeanalytics/v2/youtubeanalytics-gen.go

The difference with the original library below:
- Original Code
```
// Query: Retrieve your YouTube Analytics reports.
func (r *ReportsService) Query() *ReportsQueryCall {
	c := &ReportsQueryCall{s: r.s, urlParams_: make(gensupport.URLParams)}
	return c
}
```

- Sephora Code
```
// Query: Retrieve your YouTube Analytics reports.
func (r *ReportsService) Query(ids string, startDate string, endDate string, metrics string, dimensions string) *ReportsQueryCall {
	c := &ReportsQueryCall{s: r.s, urlParams_: make(gensupport.URLParams)}
	c.urlParams_.Set("ids", ids)
	c.urlParams_.Set("start-date", startDate)
	c.urlParams_.Set("end-date", endDate)
	c.urlParams_.Set("metrics", metrics)
	c.urlParams_.Set("dimensions", dimensions)
	return c
}
```

This allows us to have custom reports including dimensions.

## Installing Go

```
wget https://storage.googleapis.com/golang/go1.7.1.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.7.1.linux-amd64.tar.gz
echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc && source ~/.bashrc
mkdir ~/go && echo "export GOPATH=~/go" >> ~/.bashrc && source ~/.bashrc

```
